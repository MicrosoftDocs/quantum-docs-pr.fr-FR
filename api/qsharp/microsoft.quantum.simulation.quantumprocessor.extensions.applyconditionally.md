---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Opération ApplyConditionally
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 67a4dcba5c193222c06ab429813adf12d7bbedfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847899"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="b3ef4-102">Opération ApplyConditionally</span><span class="sxs-lookup"><span data-stu-id="b3ef4-102">ApplyConditionally operation</span></span>

<span data-ttu-id="b3ef4-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b3ef4-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b3ef4-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b3ef4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="b3ef4-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="b3ef4-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="b3ef4-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="b3ef4-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="b3ef4-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="b3ef4-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="b3ef4-108">onEqualOp : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3ef4-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="b3ef4-109">equalArg : 't</span><span class="sxs-lookup"><span data-stu-id="b3ef4-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="b3ef4-110">onNonEqualOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3ef4-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="b3ef4-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="b3ef4-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="b3ef4-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3ef4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b3ef4-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b3ef4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b3ef4-114">Peut</span><span class="sxs-lookup"><span data-stu-id="b3ef4-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="b3ef4-115">'U</span><span class="sxs-lookup"><span data-stu-id="b3ef4-115">'U</span></span>

