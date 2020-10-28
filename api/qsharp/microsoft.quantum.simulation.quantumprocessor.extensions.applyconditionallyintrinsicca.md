---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: Opération ApplyConditionallyIntrinsicCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 7cdddba45824d5e5037270d8578f2cb16c03be83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706619"
---
# <a name="applyconditionallyintrinsicca-operation"></a>Opération ApplyConditionallyIntrinsicCA

Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Packages [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit
```


## <a name="input"></a>Entrée

### <a name="measurementresults--__invalidresult__"></a>measurementResults : [] __non valide <Result>__




### <a name="resultsvalues--__invalidresult__"></a>resultsValues : [] __non valide <Result>__




### <a name="onequalop--unit--unit-ctl--adj"></a>onEqualOp : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + adj




### <a name="onnonequalop--unit--unit-ctl--adj"></a>onNonEqualOp : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + adj





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

