---
title: 'Q # introdution'
description: 'Présentation rapide des programmes Quantum dans Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233483"
---
# <a name="q-quantum-programming-language"></a>Q # langage de programmation Quantum

Tout ce que vous devez savoir sur le langage de programmation Q # est détaillé dans le [Guide de langage q #](xref:microsoft.quantum.qsharp.index). Comme tout autre, notre [processus de conception de langage](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) est open source et les contributions sont les bienvenus.
Pour plus d’informations sur les fondations et la motivation de Q #, consultez [pourquoi est-ce que q # est nécessaire ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).  
Q # est fourni dans le cadre du kit de développement quantique (QDK) pour une présentation rapide, consultez [qu’est-ce que le QDK ?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Qu’est-ce qu’un programme Quantum ?

Un programme Quantum peut être considéré comme un ensemble particulier de sous-routines classiques qui, lorsqu’il est appelé, effectuent un calcul en interagissant avec un système Quantum ; un programme écrit en Q # ne modélise pas directement l’État Quantum, mais décrit plutôt comment un ordinateur de contrôle classique interagit avec qubits.
Cela nous permet d’être totalement agnostique quant à ce qu' *est* un État Quantum sur chaque ordinateur cible, qui peut avoir des interprétations différentes en fonction de l’ordinateur. 

Il est important de savoir que Q # n’a pas la possibilité d’inverser l’état d’un qubit ou d’autres propriétés de mécanique de Quantum directement, ce qui garantit qu’un programme Q # peut être exécuté physiquement sur un ordinateur quantique.
Au lieu de cela, un programme peut appeler des opérations telles que [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) pour extraire des informations classiques d’un qubit.

Une fois allouée, un qubit peut être passé à des opérations et des fonctions, également appelées *callables*. Dans certains cas, il s’agit de tout ce qu’un programme Q # peut faire avec un qubit ; Toutes les actions directes sur l’état d’un qubit sont toutes définies par des callables *intrinsèques* , telles que [`X`](xref:Microsoft.Quantum.Intrinsic.X) et, c’est-à-dire des [`H`](xref:Microsoft.Quantum.Intrinsic.H) callables dont les implémentations ne sont pas définies dans Q # mais qui sont plutôt définies par l’ordinateur cible. Ce que *font* réellement ces opérations n’est rendu concrète que par l’ordinateur cible que nous utilisons pour exécuter le programme Q # en particulier.

Par exemple, si vous exécutez le programme sur notre [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), le simulateur effectue les opérations mathématiques correspondantes sur le système Quantum simulé.
Mais en regardant dans le futur, lorsque l’ordinateur cible est un ordinateur Quantum réel, l’appel de ces opérations dans Q # indiquera à l’ordinateur Quantum d’effectuer les opérations *réelles* correspondantes sur le système Quantum *réel* (par exemple, des impulsions laser avec des minutages précis).

Un programme Q # regroupe ces opérations comme défini par un ordinateur cible pour créer des opérations de niveau supérieur pour exprimer le calcul Quantum.
De cette façon, Q # permet d’exprimer facilement les algorithmes Quantum et Quantum hybrides de logique sous-jacents, tout en étant également général en ce qui concerne la structure d’un ordinateur cible ou d’un simulateur.

Un exemple simple est le programme suivant, qui alloue un qubit dans l’État $ \ket {0} $, puis lui applique une opération hadarmard `H` et mesure le résultat dans la `PauliZ` base.

```qsharp
@EntryPoint()
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

Notre [katas Quantum](https://github.com/microsoft/QuantumKatas#introduction) offre une bonne introduction aux [concepts de l’informatique Quantum](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , tels que les opérations Quantum courantes et la manière de manipuler qubits. Vous trouverez d’autres exemples dans [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude).



