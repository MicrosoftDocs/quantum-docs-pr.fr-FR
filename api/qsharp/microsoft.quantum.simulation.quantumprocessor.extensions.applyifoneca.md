---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: Opération ApplyIfOneCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: d8f388698c0c6d1557c7903ec68b317728986031
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709377"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="96acf-102">Opération ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="96acf-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="96acf-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="96acf-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="96acf-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96acf-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="96acf-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="96acf-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="96acf-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="96acf-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-ctl--adj"></a><span data-ttu-id="96acf-107">onResultOneOp : t [=> liste](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="96acf-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="96acf-108">oneArg : 't</span><span class="sxs-lookup"><span data-stu-id="96acf-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="96acf-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96acf-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="96acf-110">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="96acf-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="96acf-111">Peut</span><span class="sxs-lookup"><span data-stu-id="96acf-111">'T</span></span>

