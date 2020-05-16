---
title: Utilisation des qubits
description: Description de remplissage
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430932"
---
# <a name="working-with-qubits"></a>Utilisation des qubits

Maintenant que vous avez vu une variété de différentes parties du langage Q #, nous allons nous pencher sur l’épaisseur de l’informatique et découvrir comment utiliser qubits eux-mêmes.

Notez qu’aucune de ces instructions n’est autorisée dans le corps d’une fonction.
Elles ne sont valides que dans les opérations.

## <a name="allocating-qubits"></a>Allocation de qubits

### <a name="clean-qubits"></a>Nettoyer qubits

L' `using` instruction est utilisée pour *allouer* de nouvelles qubits à utiliser au cours d’un bloc d’instructions.

L’instruction se compose du mot clé `using` , suivi d’une parenthèse ouverte `(` , d’une liaison, d’une parenthèse fermante `)` et du bloc d’instructions dans lequel le qubits est disponible.
La liaison suit le même modèle que les `let` instructions : un symbole unique ou un tuple de symboles, suivi d’un signe égal `=` et d’une valeur unique ou d’un tuple correspondant d' *initialiseurs*.

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

Les qubits alloués de cette façon commencent par l’État $ \ket {0} $. dans l’exemple ci-dessus, `register` est donc à l’État $ \ket {00000} = \ket {0} \otimes \ket \otimes \cdots \otimes {0} \ket {0} $.
À la fin du `using` bloc, toute qubits allouée par ce bloc est immédiatement désallouée et ne peut plus être utilisée.

> [!WARNING]
> Les ordinateurs cibles s’attendent à ce que les qubits se trouvent dans l’État $ \ket {0} $ immédiatement avant la désallocation, afin qu’ils puissent être réutilisés et proposés à d’autres `using` blocs pour l’allocation.
> Dans la mesure du possible, utilisez des opérations unitaires pour renvoyer tous les qubits alloués à $ \ket {0} $.
> Si nécessaire, l' @"microsoft.quantum.intrinsic.reset" opération peut être utilisée pour mesurer un qubit à la place, et pour utiliser ce résultat de mesure pour garantir que le qubit mesuré est retourné à $ \ket {0} $. Une telle mesure détruit tout enchevêtrement avec le qubits restant et peut donc avoir un impact sur le calcul.


### <a name="borrowed-qubits"></a>Qubits empruntés

L' `borrowing` instruction est utilisée pour rendre les qubits disponibles pour une utilisation temporaire, qui n’ont pas besoin d’être dans un état spécifique.

Le mécanisme d’emprunt autorise l’allocation de qubits qui peut être utilisé comme espace de travail pendant un calcul.
Ces qubits ne sont généralement pas dans un état propre, c’est-à-dire qu’ils ne sont pas nécessairement initialisés dans un état connu tel que $ \ket {0} $.
Ils sont souvent appelés qubits « modifiés », car leur état est inconnu et peut même être enchevêtré avec d’autres parties de la mémoire de l’ordinateur quantique.

La liaison suit le même modèle et les mêmes règles que celle d’une `using` instruction.
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
L’emprunteur s’engage à laisser le qubits dans le même État que celui dans lequel il se trouvait lorsqu’il a été emprunté, c’est-à-dire que son état au début et à la fin du bloc d’instructions est supposé être le même.
En particulier, cet État n’est pas nécessairement un État classique, ce qui signifie que dans la plupart des cas, les étendues d’emprunt ne doivent pas contenir de mesures. 

Lorsque vous empruntez des qubits, le système tente d’abord de remplir la demande à partir de qubits qui sont en cours d’utilisation, mais qui ne sont pas accessibles pendant le corps de l' `borrowing` instruction.
S’il n’y a pas suffisamment de qubits, il allouera de nouvelles qubits pour terminer la demande.


Parmi les cas d’utilisation connus des qubits modifiés, citons les implémentations de portes CNOTIN multicontrôlées qui requièrent uniquement très peu de qubits et l’implémentation d’incrémenteurs.
Pour voir un exemple de leur utilisation dans Q #, ou la factorisation du papier [*à l’aide de 2n + 2 qubits avec multiplication modulaire basée sur Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler et Svore 2017) pour un algorithme utilisant des qubits empruntés, consultez l' [exemple qubits emprunté](#borrowing-qubits-example) ci-dessous.


## <a name="intrinsic-operations"></a>Opérations intrinsèques

Une fois allouée, un qubit peut ensuite être passé aux fonctions et opérations.
Dans certains cas, il s’agit de tout ce qu’un programme Q # peut faire avec un qubit, car les actions qui peuvent être effectuées sont toutes définies comme des opérations.
Nous verrons ces opérations plus en détail dans les [opérations et les fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), mais pour l’instant, nous mentionnons quelques opérations utiles qui peuvent être utilisées pour interagir avec qubits.

Tout d’abord, les opérateurs Pauli à qubit unique $X $, $Y $ et $Z $ sont représentés dans Q # par les opérations intrinsèques `X` , `Y` et `Z` , chacune ayant le type `(Qubit => Unit is Adj + Ctl)` .
Comme décrit dans [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude), nous pouvons considérer $X $ et donc `X` comme une opération de retournement de bits ou non de porte.
L' `X` opération nous permet de préparer les États de la forme $ \ket{s_0 s_1 \dots S_N} $ pour certaines chaînes de bits classiques $s $ :

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
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> Plus tard, nous verrons des moyens plus compacts d’écrire cette opération qui ne nécessitent pas de contrôle de Flow manuel.

Nous pouvons également préparer des États tels que $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ et $ \ket {-} = \left (\ket {0} -\ket {1} \right)/\Sqrt {2} $ en utilisant la transformation hadarmard $H $, qui est représentée dans Q # par l’opération intrinsèque `H : (Qubit => Unit is Adj + Ctl)` :

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

## <a name="measurements"></a>Mesures

À l’aide de l' `Measure` opération, qui est une opération intrinsèque non unitaire intégrée, nous pouvons extraire les informations classiques d’un objet de type `Qubit` et assigner une valeur classique comme résultat, qui a un type réservé `Result` , indiquant que le résultat n’est plus un État Quantum.
L’entrée de `Measure` est un axe Pauli sur la sphère Bloch, représenté par une valeur de type `Pauli` (par exemple `PauliX` ) et une valeur de type `Qubit` .

Un exemple simple est l’opération suivante, qui alloue un qubit dans l’État $ \ket {0} $, puis lui applique une opération hadarmard `H` et mesure le résultat dans la `PauliZ` base.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
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

## <a name="borrowing-qubits-example"></a>Exemple d’emprunt d’qubits

Dans l’Canon, il existe des exemples qui utilisent le `borrowing` mot clé, par exemple la fonction `MultiControlledXBorrow` définie ci-dessous.
Si `controls` dénote le contrôle qubits qui doit être ajouté à une `X` opération, un `Length(controls)-2` grand nombre de ancillas d’intégrité incorrects seront ajoutés par cette implémentation.

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

Notez que l’utilisation intensive de l' `With` ---combinable dans sa forme applicable pour les opérations qui prennent en charge joint, c’est-à-dire, `WithA` ---a été effectuée dans cet exemple.
Il s’agit d’un bon style de programmation, car l’ajout d’un contrôle à des structures impliquant `With` des propagations contrôle uniquement à l’opération interne.
Notez également que, en plus du `body` de l’opération, une implémentation du `controlled` corps de l’opération a été explicitement fournie, plutôt que de recourir à une `controlled auto` instruction.
Cela est dû au fait que nous savons à partir de la structure du circuit comment ajouter facilement des contrôles supplémentaires, ce qui est avantageux par rapport à l’ajout de contrôle à chaque porte individuelle dans le `body` . 

Il est intéressant de comparer ce code avec une autre fonction Canon `MultiControlledXClean` qui atteint le même objectif de l’implémentation d’une opération à contrôle multiple `X` , mais qui utilise plusieurs qubits propres à l’aide du `using` mécanisme. 

## <a name="whats-next"></a>Étape suivante
En savoir plus sur [le workflow de contrôle](xref:microsoft.quantum.guide.controlflow) dans Q #.