---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Opération ApplyConditionallyA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 8117fd632b78c24c9ecb8545274eaf296645b645
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230410"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="a09a5-102">Opération ApplyConditionallyA</span><span class="sxs-lookup"><span data-stu-id="a09a5-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="a09a5-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a09a5-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a09a5-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a09a5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a09a5-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="a09a5-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="a09a5-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="a09a5-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="a09a5-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="a09a5-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="a09a5-108">onEqualOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="a09a5-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="a09a5-109">equalArg : 't</span><span class="sxs-lookup"><span data-stu-id="a09a5-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="a09a5-110">onNonEqualOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="a09a5-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="a09a5-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="a09a5-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="a09a5-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a09a5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a09a5-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a09a5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a09a5-114">Peut</span><span class="sxs-lookup"><span data-stu-id="a09a5-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="a09a5-115">'U</span><span class="sxs-lookup"><span data-stu-id="a09a5-115">'U</span></span>

