---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Opération ApplyToElementA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208871"
---
# <a name="applytoelementa-operation"></a>Opération ApplyToElementA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération à un élément donné d’un tableau.

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Description

À partir d’une opération `op` , d’un index `index` et d’un tableau de cibles `targets` , s’applique `op(targets[index])` .

## <a name="input"></a>Entrée

### <a name="op--t--unit--is-adj"></a>OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération à appliquer.


### <a name="index--int"></a>index : [int](xref:microsoft.quantum.lang-ref.int)

Index dans le tableau de cibles.


### <a name="targets--t"></a>cibles : 't []

Tableau de cibles possibles pour `op` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération à appliquer.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. Quantum. Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. Quantum. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)