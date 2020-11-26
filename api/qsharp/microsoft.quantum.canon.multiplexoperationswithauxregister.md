---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Opération MultiplexOperationsWithAuxRegister
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 530e78ba0c5ce6e0627177527daf2ccc56f537eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205981"
---
# <a name="multiplexoperationswithauxregister-operation"></a>Opération MultiplexOperationsWithAuxRegister

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Étape d’implémentation de MultiplexOperations.

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="unitaries--t--unit--is-adj--ctl"></a>unités : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL []




### <a name="auxillaryregister--qubit"></a>auxillaryRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>cible : 't





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. MultiplexOperations](xref:Microsoft.Quantum.Canon.MultiplexOperations)