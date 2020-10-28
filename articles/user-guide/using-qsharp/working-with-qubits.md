---
title: Utilisation des qubits
description: En savoir plus sur l’utilisation de qubits dans Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9a3d7e03016332a04ac9d1610428b6fcd546d1f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691580"
---
# <a name="working-with-qubits"></a>Utilisation des qubits

Qubits sont l’objet fondamental des informations dans quantum computing. Pour obtenir une présentation générale de qubits, consultez Présentation de l' [informatique quantique](xref:microsoft.quantum.overview.understanding)et pour approfondir la représentation mathématique de cette vue, consultez [qubit](xref:microsoft.quantum.concepts.qubit). 

Cet article explore l’utilisation de et de l’utilisation de qubits dans un Q# programme. 

> [!IMPORTANT]
>Aucune des instructions décrites dans cet article n’est valide dans le corps d’une fonction. Elles ne sont valides que dans les opérations.

## <a name="allocating-qubits"></a>Allocation de qubits

Étant donné que les qubits physiques sont une ressource précieuse dans un ordinateur quantique, une partie du travail du compilateur consiste à s’assurer qu’ils sont utilisés aussi efficacement que possible.
Par conséquent, vous devez demander Q# à d' *allouer* qubits pour une utilisation dans un bloc d’instructions particulier.
Vous pouvez allouer qubits comme un qubit unique, ou comme un tableau de qubits, connu sous le nom de *Registre* . 

### <a name="clean-qubits"></a>Nettoyer qubits

Utilisez l' `using` instruction pour allouer de nouvelles qubits à utiliser au cours d’un bloc d’instructions.

L’instruction se compose du mot clé `using` , suivi d’une liaison placée entre parenthèses `( )` et du bloc d’instructions dans lequel les qubits sont disponibles.
La liaison suit le même modèle que les `let` instructions : un symbole unique ou un tuple de symboles, suivi d’un signe égal `=` et d’une valeur unique ou d’un tuple correspondant d' *initialiseurs* .

Les initialiseurs sont disponibles pour un qubit unique, indiqué comme `Qubit()` , ou un tableau de qubits, `Qubit[n]` , où `n` est une `Int` expression.
Par exemple,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Les qubits alloués de cette façon commencent par l’État $ \ket {0} $. Ainsi, dans l’exemple précédent, `auxiliary` est un qubit unique dans l’État $ \ket {0} $ et `register` est dans l’État cinq qubit $ \ket {00000} = \ket {0} \otimes {0} {0} \ket \otimes \cdots \otimes $.
À la fin du `using` bloc, toute qubits allouée par ce bloc est immédiatement désallouée et ne peut plus être utilisée.

> [!WARNING]
> Les ordinateurs cibles peuvent réutiliser les qubits désalloués et les proposer à d’autres `using` blocs pour l’allocation. Par conséquent, l’ordinateur cible s’attend à ce que qubits se trouve dans l’État $ \ket {0} $ immédiatement avant la désallocation.
> Dans la mesure du possible, utilisez des opérations unitaires pour renvoyer tous les qubits alloués à $ \ket {0} $.
> Si nécessaire, vous pouvez utiliser l' @"microsoft.quantum.intrinsic.reset" opération, qui retourne qubit à $ \ket {0} $ en le mesurant et en effectuant une opération de manière conditionnelle en fonction du résultat. Une telle mesure détruit tout enchevêtrement avec le qubits restant et peut donc avoir un impact sur le calcul.


### <a name="borrowed-qubits"></a>Qubits empruntés

Utilisez l' `borrowing` instruction pour allouer des qubits pour une utilisation temporaire, qui n’ont pas besoin d’être dans un état spécifique.

Vous pouvez utiliser des qubits empruntés comme espace de travail pendant un calcul.
Ces qubits ne sont généralement pas dans un état propre, autrement dit, ils ne sont pas nécessairement initialisés dans un état connu tel que $ \ket {0} $.
Ils sont souvent appelés qubits « modifiés », car leur état est inconnu et peut même être enchevêtré avec d’autres parties de la mémoire de l’ordinateur quantique.

La liaison suit le même modèle et les mêmes règles que l' `using` instruction.
Par exemple,
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
Le qubits emprunté est dans un état inconnu et est hors de portée à la fin du bloc d’instructions.
L’emprunteur s’engage à laisser le qubits dans le même État que celui dans lequel il se trouvait lorsqu’il les a empruntés ; autrement dit, leur état au début et à la fin du bloc d’instructions doit être le même.
Étant donné que cet État n’est pas nécessairement un État classique, dans la plupart des cas, les étendues de emprunt ne doivent pas contenir de mesures. 

Lorsque vous empruntez des qubits, le système tente d’abord de remplir la demande à partir de qubits qui sont en cours d’utilisation, mais qui ne sont pas accessibles pendant le corps de l' `borrowing` instruction.
S’il n’y a pas suffisamment de qubits, il alloue de nouveaux qubits pour terminer la demande.

Parmi les cas d’utilisation connus des qubits modifiés, citons les implémentations de portes CNOTIN multicontrôlées qui requièrent uniquement très peu de qubits et l’implémentation d’incrémenteurs.
Pour obtenir un exemple de leur utilisation dans Q# , consultez l' [exemple emprunting qubits](#borrowing-qubits-example) dans cet article, ou la [*factorisation papier à l’aide de 2n + 2 qubits avec la multiplication modulaire basée sur Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler et Svore 2017) pour un algorithme qui utilise des qubits empruntés.

## <a name="intrinsic-operations"></a>Opérations intrinsèques

Une fois allouée, vous pouvez passer un qubit à des fonctions et des opérations.
Dans certains cas, il s’agit de tout ce qu’un Q# programme peut faire avec un qubit, car les actions qui peuvent être effectuées sont toutes définies comme des opérations.

Cet article présente quelques Q# opérations utiles que vous pouvez utiliser pour interagir avec qubits.
Pour plus d’informations sur ces éléments et d’autres, consultez [fonctions et opérations intrinsèques](xref:microsoft.quantum.libraries.standard.prelude). 

Tout d’abord, les opérateurs Pauli à qubit unique $X $, $Y $ et $Z $ sont représentés Q# par les opérations intrinsèques [`X`](xref:Microsoft.Quantum.Intrinsic.X) , [`Y`](xref:Microsoft.Quantum.Intrinsic.Y) et [`Z`](xref:Microsoft.Quantum.Intrinsic.Z) , chacune d’elles ayant le type `(Qubit => Unit is Adj + Ctl)` .

Comme décrit dans [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), imaginez $X $ et, par conséquent, `X` une opération de retournement de bits ou pas de porte.
Vous pouvez utiliser l' `X` opération pour préparer les États de la forme $ \ket{s_0 s_1 \dots S_N} $ pour certaines chaînes de bits classiques $s $ :

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

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> Plus tard, vous verrez des méthodes plus compactes pour l’écriture de cette opération qui ne nécessitent pas de contrôle manuel.

Vous pouvez également préparer des États tels que $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ et $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\Sqrt {2} $ en utilisant la transformation hadarmard $H $, qui est représentée Q# par l’opération intrinsèque [`H`](xref:Microsoft.Quantum.Intrinsic.H) (également de type (qubit => unité est Adj + CTL) ') :

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Mesures

Les mesures des qubits individuelles peuvent être effectuées dans différentes bases, chacune représentée par un axe Pauli sur la [sphère Bloch](xref:microsoft.quantum.glossary#bloch-sphere).
La base de *calcul* fait référence à la base `PauliZ` et est la base la plus courante utilisée pour la mesure.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Mesure d’un qubit unique dans la `PauliZ` base

Utilisez l' [`M`](xref:Microsoft.Quantum.Intrinsic.M) opération, qui est une opération intrinsèque non unitaire intégrée, pour mesurer un qubit unique dans la `PauliZ` base et assigner une valeur classique au résultat.
`M` a un type de retour réservé, `Result` , qui peut uniquement prendre des valeurs `Zero` ou `One` correspond aux États mesurés $ \ket {0} $ ou $ \ket {1} $-indiquant que le résultat n’est plus un État Quantum.

Un exemple simple est l’opération suivante, qui alloue un qubit dans l’État $ \ket {0} $, puis lui applique une opération hadarmard `H` et mesure le résultat dans la `PauliZ` base.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Mesure d’un ou plusieurs qubits dans des bases spécifiques

Pour mesurer un tableau d’un ou plusieurs qubits dans des bases spécifiques, vous pouvez utiliser l' [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) opération.

Les entrées de `Measure` sont un tableau de `Pauli` types (par exemple, `[PauliX, PauliZ, PauliZ]` ) et un tableau de qubits.

Un exemple légèrement plus compliqué est donné par l’opération suivante, qui retourne la valeur booléenne `true` si tous les qubits dans un registre de type `Qubit[]` sont dans l’état zéro lorsqu’ils sont mesurés dans une base de Pauli spécifiée, et qui retourne `false` sinon.

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

Notez que cet exemple s’exécute toujours uniquement `Measure` sur des qubits individuels, mais l’opération peut être étendue à des mesures communes sur plusieurs qubits.

## <a name="borrowing-qubits-example"></a>Exemple d’emprunt d’qubits

L’Canon contient des exemples qui utilisent le `borrowing` mot clé, comme la fonction suivante `MultiControlledXBorrow` . Si `controls` indique que le contrôle qubits à ajouter à une `X` opération, le nombre de [ancillas](xref:microsoft.quantum.glossary#ancilla) de modifications ajoutés par cette implémentation est `Length(controls)-2` .

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

Notez que cet exemple utilise une utilisation intensive du `With` combinateur, sous sa forme applicable pour les opérations qui prennent en charge joint, par exemple, `WithA` .
Il s’agit d’un bon style de programmation, car l’ajout d’un contrôle à des structures impliquant `With` des propagations contrôle uniquement à l’opération interne.
Notez également que, en plus de l' `body` opération, une implémentation du `controlled` corps de l’opération a été fournie explicitement, plutôt que de recourir à une `controlled auto` instruction.
Cela est dû au fait que, en raison de la structure du circuit, il est facile d’ajouter des contrôles supplémentaires, ce qui est avantageux par rapport à l’ajout du contrôle à chaque porte dans le `body` . 

Il est intéressant de comparer ce code avec une autre fonction Canon `MultiControlledXClean` qui atteint le même objectif de l’implémentation d’une opération à contrôle multiple `X` , mais qui utilise plusieurs qubits propres à l’aide du `using` mécanisme. 

## <a name="next-steps"></a>Étapes suivantes

En savoir plus sur [le workflow de contrôle](xref:microsoft.quantum.guide.controlflow) dans Q# .