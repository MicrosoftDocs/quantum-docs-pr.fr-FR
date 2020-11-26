---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: Opération ApplyIfElseR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: 9e391b61aa4d22ad02bf657a866f959d35b6628f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192670"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="6a7d9-102">Opération ApplyIfElseR</span><span class="sxs-lookup"><span data-stu-id="6a7d9-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="6a7d9-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="6a7d9-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6a7d9-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6a7d9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="6a7d9-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="6a7d9-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="6a7d9-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="6a7d9-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="6a7d9-107">onResultZeroOp : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a7d9-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="6a7d9-108">zeroArg : 't</span><span class="sxs-lookup"><span data-stu-id="6a7d9-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="6a7d9-109">onResultOneOp : 'U => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a7d9-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="6a7d9-110">oneArg : 'U</span><span class="sxs-lookup"><span data-stu-id="6a7d9-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="6a7d9-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a7d9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6a7d9-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6a7d9-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a7d9-113">Peut</span><span class="sxs-lookup"><span data-stu-id="6a7d9-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="6a7d9-114">'U</span><span class="sxs-lookup"><span data-stu-id="6a7d9-114">'U</span></span>

