---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Opération ApplyConditionally
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: fe623b240e35ee88f673b6e90db6307ef701d049
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701710"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="d446c-102">Opération ApplyConditionally</span><span class="sxs-lookup"><span data-stu-id="d446c-102">ApplyConditionally operation</span></span>

<span data-ttu-id="d446c-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="d446c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d446c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d446c-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="d446c-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="d446c-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="d446c-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="d446c-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="d446c-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="d446c-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="d446c-108">onEqualOp : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d446c-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="d446c-109">equalArg : 't</span><span class="sxs-lookup"><span data-stu-id="d446c-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="d446c-110">onNonEqualOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d446c-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="d446c-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="d446c-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="d446c-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d446c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d446c-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d446c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d446c-114">Peut</span><span class="sxs-lookup"><span data-stu-id="d446c-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="d446c-115">'U</span><span class="sxs-lookup"><span data-stu-id="d446c-115">'U</span></span>

