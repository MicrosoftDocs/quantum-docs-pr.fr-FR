---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Opération ApplySeriesOfOpsC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: 308256833dc607f685e3a5f2278e374cf3b6ce22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844643"
---
# <a name="applyseriesofopsc-operation"></a>Opération ApplySeriesOfOpsC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau. Contrôl

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Entrée

### <a name="listofops--t--unit--is-ctl"></a>listOfOps : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL []

Liste des opérations, chacune utilisant un tableau t, à appliquer. Elles sont appliquées séquentiellement, le plus bas en premier.
Chaque doit avoir un functor contrôlé


### <a name="targets--int"></a>cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []

Tableaux imbriqués décrivant les cibles du op. Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.


### <a name="register--t"></a>inscrire : 't []

Qubit Inscrivez-vous pour être traité.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="example"></a>Exemple

L’exemple suivant applique exp ([PauliX, PauliY], 0,5) à qubits 0, 1//Then X à qubit 2 Let OPS = [exp ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitC (X, _)]; Let index = [[0, 1], [2]]; ApplySeriesOfOpsC (OPS, index, qubitArray);

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)