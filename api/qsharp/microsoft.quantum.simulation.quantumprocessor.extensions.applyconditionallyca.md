---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Opération ApplyConditionallyCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: e456ed5d8f7f17a914401473948c89c020174903
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706646"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="77458-102">Opération ApplyConditionallyCA</span><span class="sxs-lookup"><span data-stu-id="77458-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="77458-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="77458-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="77458-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77458-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="77458-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="77458-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="77458-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="77458-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="77458-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="77458-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-ctl--adj"></a><span data-ttu-id="77458-108">onEqualOp : t [=> liste](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="77458-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="77458-109">equalArg : 't</span><span class="sxs-lookup"><span data-stu-id="77458-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-ctl--adj"></a><span data-ttu-id="77458-110">onNonEqualOp : 'U [=> liste](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="77458-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="77458-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="77458-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="77458-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77458-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="77458-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="77458-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77458-114">Peut</span><span class="sxs-lookup"><span data-stu-id="77458-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="77458-115">'U</span><span class="sxs-lookup"><span data-stu-id="77458-115">'U</span></span>

