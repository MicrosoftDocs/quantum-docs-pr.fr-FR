---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: Opération ApplyIfElseRC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: b2e4ade84b25b0100fe4b69814c760a672833f06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209483"
---
# <a name="applyifelserc-operation"></a>Opération ApplyIfElseRC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique l’une des deux opérations contrôlable, en fonction de la valeur d’un résultat classique.

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Description

Avec un résultat donné `result` , applique l’opération `zeroOp` avec `zeroInput` comme entrée lorsque `result` est égal à `Zero` et s’applique `oneOp(oneInput)` quand `result == One` .

## <a name="input"></a>Entrée

### <a name="result--__invalidresult__"></a>résultat : __non <Result> valide__

Résultat de mesure utilisé pour déterminer si `zeroOp` ou `oneOp` est appliqué.


### <a name="zeroop--t--unit--is-ctl"></a>zeroOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL

Opération contrôlable à appliquer lorsque `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput : 't

Entrée à fournir `zeroOp` lorsque `result == Zero` .


### <a name="oneop--u--unit--is-ctl"></a>oneOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL

Opération contrôlable à appliquer lorsque `result == One` .


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