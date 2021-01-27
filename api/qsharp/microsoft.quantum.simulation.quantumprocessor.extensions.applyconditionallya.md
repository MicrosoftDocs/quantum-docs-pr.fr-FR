---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Opération ApplyConditionallyA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 18ea79e363c28d4fa7aacb69d53a43f6ce39df36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847871"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="78aee-102">Opération ApplyConditionallyA</span><span class="sxs-lookup"><span data-stu-id="78aee-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="78aee-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="78aee-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="78aee-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="78aee-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="78aee-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="78aee-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="78aee-106">measurementResults : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="78aee-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="78aee-107">resultsValues : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="78aee-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="78aee-108">onEqualOp : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="78aee-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="78aee-109">equalArg : 't</span><span class="sxs-lookup"><span data-stu-id="78aee-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="78aee-110">onNonEqualOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="78aee-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="78aee-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="78aee-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="78aee-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78aee-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="78aee-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="78aee-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="78aee-114">Peut</span><span class="sxs-lookup"><span data-stu-id="78aee-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="78aee-115">'U</span><span class="sxs-lookup"><span data-stu-id="78aee-115">'U</span></span>

