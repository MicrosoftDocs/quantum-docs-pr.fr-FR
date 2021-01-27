---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: Opération ApplyIfElseB
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 3eba3822a95939d210c5a05dd1efa80f1aa57374
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841838"
---
# <a name="applyifelseb-operation"></a>Opération ApplyIfElseB

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique l’une des deux opérations, en fonction de la valeur d’un bit classique.

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a>Description

À partir d’un bit `bit` , applique l’opération `trueOp` avec `trueInput` comme entrée lorsque `bit` est `true` et s’applique `falseOp(falseInput)` lorsque `bit` est `false` .

## <a name="input"></a>Entrée

### <a name="bit--bool"></a>bit : [bool](xref:microsoft.quantum.lang-ref.bool)

Valeur booléenne utilisée pour déterminer si `trueOp` ou `falseOp` est appliqué.


### <a name="trueop--t--unit"></a>trueOp : 't => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération à appliquer lorsque a la `bit` valeur `true` .


### <a name="trueinput--t"></a>trueInput : 't

Entrée à fournir `trueOp` lorsque a la valeur `bit` `true` .


### <a name="falseop--u--unit"></a>falseOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération à appliquer lorsque a la `bit` valeur `false` .


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