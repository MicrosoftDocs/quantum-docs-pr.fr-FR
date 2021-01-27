---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsic
title: Opération ApplyConditionallyIntrinsic
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsic
qsharp.summary: ''
ms.openlocfilehash: 2301ef25a262ead63c3550777af79e1d3f9c5a98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858490"
---
# <a name="applyconditionallyintrinsic-operation"></a><span data-ttu-id="dd4fd-102">Opération ApplyConditionallyIntrinsic</span><span class="sxs-lookup"><span data-stu-id="dd4fd-102">ApplyConditionallyIntrinsic operation</span></span>

<span data-ttu-id="dd4fd-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="dd4fd-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="dd4fd-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dd4fd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsic (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit), onNonEqualOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="dd4fd-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="dd4fd-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="dd4fd-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="dd4fd-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="dd4fd-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="dd4fd-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit"></a><span data-ttu-id="dd4fd-108">onEqualOp : [](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) unité d’unité</span><span class="sxs-lookup"><span data-stu-id="dd4fd-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onnonequalop--unit--unit"></a><span data-ttu-id="dd4fd-109">onNonEqualOp : [](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) unité d’unité</span><span class="sxs-lookup"><span data-stu-id="dd4fd-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="dd4fd-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd4fd-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

