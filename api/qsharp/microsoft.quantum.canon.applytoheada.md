---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Opération ApplyToHeadA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208633"
---
# <a name="applytoheada-operation"></a>Opération ApplyToHeadA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération au premier élément d’un tableau.

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Description

Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Head(targets))` .

## <a name="input"></a>Entrée

### <a name="op--t--unit--is-adj"></a>OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération à appliquer.


### <a name="targets--t"></a>cibles : 't []

Tableau de cibles, auquel le premier sera appliqué `op` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à appliquer.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. Quantum. Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. Quantum. Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)