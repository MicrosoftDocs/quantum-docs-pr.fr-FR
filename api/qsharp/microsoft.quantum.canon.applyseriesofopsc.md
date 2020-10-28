---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Opération ApplySeriesOfOpsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705014"
---
# <a name="applyseriesofopsc-operation"></a>Opération ApplySeriesOfOpsC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique de façon séquentielle une liste d’opérations et leurs cibles sur un tableau. Contrôl

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="listofops--t--unit-ctl"></a>listOfOps : 't [] => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit) []

Liste des opérations, chacune utilisant un tableau t, à appliquer. Elles sont appliquées séquentiellement, le plus bas en premier.
Chaque doit avoir un functor contrôlé


### <a name="targets--int"></a>cibles : [int](xref:microsoft.quantum.lang-ref.int)[] []

Tableaux imbriqués décrivant les cibles du op. Chaque tableau doit contenir une liste d’entiers qui décrivent les index à utiliser.


### <a name="register--t"></a>inscrire : 't []

Qubit Inscrivez-vous pour être traité.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)