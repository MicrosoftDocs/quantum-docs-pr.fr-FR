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
# <a name="applyconditionallya-operation"></a><span data-ttu-id="ac8a0-102">Opération ApplyConditionallyA</span><span class="sxs-lookup"><span data-stu-id="ac8a0-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="ac8a0-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="ac8a0-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="ac8a0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac8a0-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="ac8a0-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="ac8a0-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="ac8a0-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="ac8a0-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="ac8a0-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="ac8a0-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-adj"></a><span data-ttu-id="ac8a0-108">onEqualOp : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac8a0-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="ac8a0-109">equalArg : 't</span><span class="sxs-lookup"><span data-stu-id="ac8a0-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-adj"></a><span data-ttu-id="ac8a0-110">onNonEqualOp : 'U => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac8a0-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="ac8a0-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="ac8a0-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ac8a0-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac8a0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ac8a0-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ac8a0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac8a0-114">Peut</span><span class="sxs-lookup"><span data-stu-id="ac8a0-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="ac8a0-115">'U</span><span class="sxs-lookup"><span data-stu-id="ac8a0-115">'U</span></span>

