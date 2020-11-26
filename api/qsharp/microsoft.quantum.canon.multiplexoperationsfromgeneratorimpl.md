---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGeneratorImpl
title: Opération MultiplexOperationsFromGeneratorImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGeneratorImpl
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 98ba9cd24f04b8417cb176ee1630402483bc3b52
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206049"
---
# <a name="multiplexoperationsfromgeneratorimpl-operation"></a>Opération MultiplexOperationsFromGeneratorImpl

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Étape d’implémentation de `MultiplexOperationsFromGenerator` .

```qsharp
operation MultiplexOperationsFromGeneratorImpl<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="unitarygenerator--intintint---t--unit--is-adj--ctl"></a>unitaryGenerator : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL)




### <a name="auxiliary--qubit"></a>auxiliaire : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>cible : 't





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. MultiplexOperationsFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)