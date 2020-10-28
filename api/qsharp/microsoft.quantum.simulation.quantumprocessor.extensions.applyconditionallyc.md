---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Opération ApplyConditionallyC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: fc1cf50b7befd40cf20720032329438715a9b856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706654"
---
# <a name="applyconditionallyc-operation"></a>Opération ApplyConditionallyC

Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Packages [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Entrée

### <a name="measurementresults--__invalidresult__"></a>measurementResults : [] __non valide <Result>__




### <a name="resultsvalues--__invalidresult__"></a>resultsValues : [] __non valide <Result>__




### <a name="onequalop--t--unit-ctl"></a>onEqualOp : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)




### <a name="equalarg--t"></a>equalArg : 't




### <a name="onnonequalop--u--unit-ctl"></a>onNonEqualOp : 'U => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)




### <a name="nonequalarg--u"></a>nonEqualArg : 'U





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U

