---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Opération ApplyWithInputTransformationCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c81620555bff9449d6a3235dc7cfa56ca5206f04
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207783"
---
# <a name="applywithinputtransformationca-operation"></a>Opération ApplyWithInputTransformationCA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dans le cas d’une opération qui accepte une entrée, une fonction qui retourne une sortie compatible avec cette opération, et une entrée à cette fonction, applique l’opération à l’aide de la fonction pour transformer l’entrée en un formulaire attendu par l’opération.

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="fn--u---t"></a>FN : 'U-> '

Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.


### <a name="op--t--unit--is-adj--ctl"></a>OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération à appliquer.


### <a name="input--u"></a>entrée : 'U

Entrée de la fonction.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationC](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)