---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: Opération ApplyIfElseRCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: fb2f7ded44708a93d97d7041bf15be2c8c48990a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706459"
---
# <a name="applyifelserca-operation"></a>Opération ApplyIfElseRCA

Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Packages [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a>Entrée

### <a name="measurementresult--__invalidresult__"></a>measurementResult : __non <Result> valide__




### <a name="onresultzeroop--t--unit-adj--ctl"></a>onResultZeroOp : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="zeroarg--t"></a>zeroArg : 't




### <a name="onresultoneop--u--unit-adj--ctl"></a>onResultOneOp : 'U [=> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="onearg--u"></a>oneArg : 'U





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U

