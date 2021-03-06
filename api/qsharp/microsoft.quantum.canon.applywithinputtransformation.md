---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Opération ApplyWithInputTransformation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d4589acbe9f9dc6c6ab665582ed663dbc193edbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850374"
---
# <a name="applywithinputtransformation-operation"></a>Opération ApplyWithInputTransformation

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dans le cas d’une opération qui accepte une entrée, une fonction qui retourne une sortie compatible avec cette opération, et une entrée à cette fonction, applique l’opération à l’aide de la fonction pour transformer l’entrée en un formulaire attendu par l’opération.

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a>Entrée

### <a name="fn--u---t"></a>FN : 'U-> '

Fonction qui transforme l’entrée donnée en une forme attendue par l’opération.


### <a name="op--t--unit"></a>OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération à appliquer.


### <a name="input--u"></a>entrée : 'U

Entrée de la fonction.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U



## <a name="example"></a>Exemple

L’appel suivant utilise @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" pour appliquer une opération conçue pour des @"Microsoft.Quantum.Arithmetic.BigEndian" entrées à une entrée de type @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyWithInputTransformationA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationC](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationCA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)