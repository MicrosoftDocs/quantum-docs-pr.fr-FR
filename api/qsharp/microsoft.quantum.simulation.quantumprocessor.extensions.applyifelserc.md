---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: Opération ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701251"
---
# <a name="applyifelserc-operation"></a>Opération ApplyIfElseRC

Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Packages [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a>Entrée

### <a name="measurementresult--__invalidresult__"></a>measurementResult : __non <Result> valide__




### <a name="onresultzeroop--t--unit-ctl"></a>onResultZeroOp : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)




### <a name="zeroarg--t"></a>zeroArg : 't




### <a name="onresultoneop--u--unit-ctl"></a>onResultOneOp : 'U => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)




### <a name="onearg--u"></a>oneArg : 'U





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U

