---
title: Utilisation de qubits | Microsoft Docs
description: Utilisation de qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 477b358c3eba58b62926b4e9094770c9741cac92
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864251"
---
# <a name="working-with-qubits"></a>Utilisation de qubits #

Maintenant que vous avez vu une variété de différentes parties du langage Q #, nous allons nous pencher sur l’épaisseur de l’informatique et découvrir comment utiliser qubits eux-mêmes.

## <a name="allocating-qubits"></a>Allocation de qubits ##

Tout d’abord, pour obtenir un qubit que nous pouvons utiliser dans Q #, nous *allouez* des qubits dans un bloc de `using` :

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Les qubits alloués de cette façon commencent par l’État $ \ket{0}$; dans l’exemple ci-dessus, `register` est donc à l’État $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.
À la fin du bloc `using`, toute qubits allouée par ce bloc est immédiatement désallouée et ne peut plus être utilisée.

> [!WARNING]
> Les ordinateurs cibles s’attendent à ce que les qubits se trouvent dans l’État $ \ket{0}$ immédiatement avant la désallocation, afin qu’ils puissent être réutilisés et proposés à d’autres blocs `using` pour l’allocation.
> Dans la mesure du possible, utilisez des opérations unitaires pour renvoyer tous les qubits alloués à $ \ket{0}$.
> Si nécessaire, l’opération @"microsoft.quantum.intrinsic.reset" peut être utilisée pour mesurer un qubit à la place, et pour utiliser ce résultat de mesure pour s’assurer que le qubit mesuré est retourné à $ \ket{0}$. Une telle mesure détruit tout enchevêtrement avec le qubits restant et peut donc avoir un impact sur le calcul. 

## <a name="intrinsic-operations"></a>Opérations intrinsèques ##

Une fois allouée, un qubit peut ensuite être passé aux fonctions et opérations.
Dans certains cas, il s’agit de tout ce qu’un programme Q # peut faire avec un qubit, car les actions qui peuvent être effectuées sont toutes définies comme des opérations.
Nous verrons ces opérations plus en détail dans les [opérations et les fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), mais pour l’instant, nous mentionnons quelques opérations utiles qui peuvent être utilisées pour interagir avec qubits.

Tout d’abord, les opérateurs Pauli à qubit unique $X $, $Y $ et $Z $ sont représentés dans Q # par les opérations intrinsèques `X`, `Y`et `Z`, chacune ayant une `(Qubit => Unit is Adj + Ctl)`de type.
Comme décrit dans [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), nous pouvons considérer $X $ et, par conséquent, `X` en tant qu’opération de retournement de bits ou non de porte.
Cela nous permet de préparer les États de la forme $ \ket{s_0 s_1 \dots s_n} $ pour certaines chaînes de bits classiques $s $ :

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit 
is Adj + Ctl {

    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> Plus tard, nous verrons des moyens plus compacts d’écrire cette opération qui ne nécessitent pas de contrôle de Flow manuel.

Nous pouvons également préparer des États tels que $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ et $ \ket{-} = \left (\ket{0}-\ket{1}\right)/\sqrt{2}$ en utilisant la transformation Hadarmard $H $, qui est représentée dans Q # par l’opération intrinsèque `H : (Qubit => Unit is Adj + Ctl)`:

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {

    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Mesures ##

À l’aide de l’opération de `Measure`, qui est une opération non unitaire intrinsèque intégrée, nous pouvons extraire des informations classiques à partir d’un objet de type `Qubit` et assigner une valeur classique comme résultat, qui a un type réservé `Result`, indiquant que le résultat n’est plus un État Quantum. L’entrée de `Measure` est un axe Pauli sur la sphère Bloch, représentée par un objet de type `Pauli` (par exemple, `PauliX`) et un objet de type `Qubit`. 

Un exemple simple est l’opération suivante qui crée un qubit dans l’État $ \ket{0}$, puis applique une porte Hadarmard ``H`` et mesure le résultat dans la base de `PauliZ`. 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
        H(qubit); 
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator, 
        // we reset the qubit before releasing it. 
        if (result == One) { X(qubit); }   
        // Finally, we return the result of the measurement. 
        return result;
    }
}
```

Un exemple légèrement plus compliqué est fourni par l’opération suivante qui retourne la valeur booléenne `true` si tous les qubits dans un registre de type `Qubit[]` se trouvent dans l’état zéro, lorsqu’ils sont mesurés dans une base Pauli spécifiée et `false` dans le cas contraire. 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

Le langage Q # autorise les dépendances du workflow de contrôle classique sur les résultats de mesure de qubits. Cela permet à son tour d’implémenter des gadgets probabilistes puissants qui peuvent réduire le coût de calcul de l’implémentation des unités. En guise d’exemple, il est facile d’implémenter de la même manière, appelée *REPEAT-UNTIL-Successful* , dans Q #, qui sont des circuits probabilistes qui ont un coût faible *attendu* en termes de portes élémentaires, mais pour lesquelles le coût réel dépend d’une exécution réelle et d’un entrelacement réel de diverses branches possibles. 

Pour faciliter les modèles de répétition jusqu’à réussite (RUS), Q # prend en charge la construction
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
où `statementBlock1` et `statementBlock2` sont des instructions Q # ou plus, et `expression` toute expression valide qui correspond à une valeur de type `Bool`. Dans un cas d’usage typique, le circuit suivant implémente une rotation autour d’un axe irrationnelle de $ (I + 2i Z)/\sqrt{5}$ sur la sphère Bloch. Pour ce faire, utilisez un modèle de RUS connu : 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

Cet exemple montre l’utilisation d’une variable mutable `finished` qui se trouve dans la portée de la boucle REPEAT-UNTIL-Fixup entière et qui est initialisée avant la boucle et mise à jour à l’étape de correction.

Enfin, nous présentons un exemple de modèle de RUS pour préparer un État Quantum $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\ket{0}+ \ket{1}\right) $, à partir de l’État $ \ket{+} $. Consultez également l' [exemple de test unitaire fourni avec la bibliothèque standard](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs): 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
Les fonctionnalités de programmation notables présentées dans cette opération sont une `fixup` une partie plus complexe de la boucle qui implique des opérations de Quantum, et l’utilisation d’instructions `AssertProb` pour déterminer la probabilité de mesurer l’État Quantum à certains points spécifiés dans le programme. Pour plus d’informations sur les instructions `Assert` et `AssertProb`, voir aussi [test et débogage](xref:microsoft.quantum.techniques.testing-and-debugging) . 
