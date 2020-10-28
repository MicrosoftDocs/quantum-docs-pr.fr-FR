---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: Opération ApplyIfElseBA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: ce08907646c3210f76244f29aa0d936e2bd6ee43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705331"
---
# <a name="applyifelseba-operation"></a>Opération ApplyIfElseBA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique l’une des deux opérations adjointable, en fonction de la valeur d’un bit classique.

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit
```


## <a name="description"></a>Description

À partir d’un bit `bit` , applique l’opération `trueOp` avec `trueInput` comme entrée lorsque `bit` est `true` et s’applique `falseOp(falseInput)` lorsque `bit` est `false` .

## <a name="input"></a>Entrée

### <a name="bit--bool"></a>bit : [bool](xref:microsoft.quantum.lang-ref.bool)

Valeur booléenne utilisée pour déterminer si `trueOp` ou `falseOp` est appliqué.


### <a name="trueop--t--unit-adj"></a>trueOp : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération adjointable à appliquer lorsque a la `bit` valeur `true` .


### <a name="trueinput--t"></a>trueInput : 't

Entrée à fournir `trueOp` lorsque a la valeur `bit` `true` .


### <a name="falseop--u--unit-adj"></a>falseOp : 'U => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération adjointable à appliquer lorsque a la `bit` valeur `false` .


### <a name="falseinput--u"></a>falseInput : 'U

Entrée à fournir `falseOp` lorsque a la valeur `bit` `false` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type d’entrée de l’opération `trueOp` à appliquer de façon conditionnelle.
### <a name="u"></a>'U

Type d’entrée de l’opération `falseOp` à appliquer de façon conditionnelle.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)