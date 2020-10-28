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
# <a name="applyconditionallyintrinsicca-operation"></a><span data-ttu-id="8f056-102">Opération ApplyConditionallyIntrinsicCA</span><span class="sxs-lookup"><span data-stu-id="8f056-102">ApplyConditionallyIntrinsicCA operation</span></span>

<span data-ttu-id="8f056-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="8f056-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="8f056-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f056-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="8f056-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="8f056-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="8f056-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="8f056-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="8f056-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="8f056-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit-ctl--adj"></a><span data-ttu-id="8f056-108">onEqualOp : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="8f056-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="onnonequalop--unit--unit-ctl--adj"></a><span data-ttu-id="8f056-109">onNonEqualOp : liste [d’unités](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="8f056-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="8f056-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f056-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

