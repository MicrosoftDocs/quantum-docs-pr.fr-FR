---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Opération ApplyConditionallyA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: b6f7e7d6d51e531b0ec9e7e4f2f5772038421933
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701707"
---
# <a name="applyconditionallya-operation"></a>Opération ApplyConditionallyA

Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Packages [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Entrée

### <a name="measurementresults--__invalidresult__"></a>measurementResults : [] __non valide <Result>__




### <a name="resultsvalues--__invalidresult__"></a>resultsValues : [] __non valide <Result>__




### <a name="onequalop--t--unit-adj"></a>onEqualOp : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)




### <a name="equalarg--t"></a>equalArg : 't




### <a name="onnonequalop--u--unit-adj"></a>onNonEqualOp : 'U => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)




### <a name="nonequalarg--u"></a>nonEqualArg : 'U





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut


### <a name="u"></a>'U

