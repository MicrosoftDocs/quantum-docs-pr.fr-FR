---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Opération ApplyConditionallyCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: 18db01f8e5e00c2f115b8ffe73c0f8eea275beb0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230240"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="08828-102">Opération ApplyConditionallyCA</span><span class="sxs-lookup"><span data-stu-id="08828-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="08828-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="08828-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="08828-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="08828-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="08828-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="08828-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="08828-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="08828-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="08828-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="08828-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj--ctl"></a><span data-ttu-id="08828-108">onEqualOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="08828-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="08828-109">equalArg : 't</span><span class="sxs-lookup"><span data-stu-id="08828-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj--ctl"></a><span data-ttu-id="08828-110">onNonEqualOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="08828-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="08828-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="08828-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="08828-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="08828-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="08828-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="08828-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="08828-114">Peut</span><span class="sxs-lookup"><span data-stu-id="08828-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="08828-115">'U</span><span class="sxs-lookup"><span data-stu-id="08828-115">'U</span></span>

