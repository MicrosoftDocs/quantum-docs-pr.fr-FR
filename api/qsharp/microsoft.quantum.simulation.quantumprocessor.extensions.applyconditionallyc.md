---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Opération ApplyConditionallyC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 963a85e0e442592c01a2e70fa0dc02d6048d8be7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229033"
---
# <a name="applyconditionallyc-operation"></a>Opération ApplyConditionallyC

Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a>Entrée

### <a name="measurementresults--__invalidresult__"></a>measurementResults : [] __non valide <Result>__




### <a name="resultsvalues--__invalidresult__"></a>resultsValues : [] __non valide <Result>__




### <a name="onequalop--t--unit--is-ctl"></a>onEqualOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL




### <a name="equalarg--t"></a>equalArg : 't




### <a name="onnonequalop--u--unit--is-ctl"></a>onNonEqualOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL




### <a name="nonequalarg--u"></a>nonEqualArg : 'U





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U

