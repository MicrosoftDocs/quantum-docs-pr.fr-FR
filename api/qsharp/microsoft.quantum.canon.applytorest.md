---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Opération ApplyToRest
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: fe49361f3c2259960eaa58d47df9b69b30b572a8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208262"
---
# <a name="applytorest-operation"></a>Opération ApplyToRest

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération à tous les éléments à l’exception du premier élément d’un tableau.

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Description

Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Rest(targets))` .

## <a name="input"></a>Entrée

### <a name="op--t--unit"></a>OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération à appliquer.


### <a name="targets--t"></a>cibles : 't []

Tableau de cibles, dont tous les sauf le premier seront appliqués `op` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à appliquer.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToRestA](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft. Quantum. Canon. ApplyToRestC](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [Microsoft. Quantum. Canon. ApplyToRestCA](xref:Microsoft.Quantum.Canon.ApplyToRestCA)