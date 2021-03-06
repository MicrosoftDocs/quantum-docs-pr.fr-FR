---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Opération ApplyIfElseRA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 0a7683adfa15f787f96c7ae55f94e2c52426df75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845013"
---
# <a name="applyifelsera-operation"></a>Opération ApplyIfElseRA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique l’une des deux opérations adjointable, en fonction de la valeur d’un résultat classique.

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a>Description

Avec un résultat donné `result` , applique l’opération `zeroOp` avec `zeroInput` comme entrée lorsque `result` est égal à `Zero` et s’applique `oneOp(oneInput)` quand `result == One` .

## <a name="input"></a>Entrée

### <a name="result--__invalidresult__"></a>résultat : __non <Result> valide__

Résultat de mesure utilisé pour déterminer si `zeroOp` ou `oneOp` est appliqué.


### <a name="zeroop--t--unit--is-adj"></a>zeroOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération adjointable à appliquer lorsque `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput : 't

Entrée à fournir `zeroOp` lorsque `result == Zero` .


### <a name="oneop--u--unit--is-adj"></a>oneOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération adjointable à appliquer lorsque `result == One` .


### <a name="oneinput--u"></a>oneInput : 'U

Entrée à fournir `oneOp` lorsque `result == One` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération `zeroOp` à appliquer de façon conditionnelle.
### <a name="u"></a>'U

Type d’entrée de l’opération `oneOp` à appliquer de façon conditionnelle.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)