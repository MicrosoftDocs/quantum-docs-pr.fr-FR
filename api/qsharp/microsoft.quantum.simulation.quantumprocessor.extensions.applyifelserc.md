---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: Opération ApplyIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701251"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="ab69a-102">Opération ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="ab69a-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="ab69a-103">Espace de noms : [Microsoft. Quantum. simulation. QuantumProcessor. extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="ab69a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="ab69a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab69a-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="ab69a-105">Entrée</span><span class="sxs-lookup"><span data-stu-id="ab69a-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="ab69a-106">measurementResult : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="ab69a-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl"></a><span data-ttu-id="ab69a-107">onResultZeroOp : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab69a-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="ab69a-108">zeroArg : 't</span><span class="sxs-lookup"><span data-stu-id="ab69a-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-ctl"></a><span data-ttu-id="ab69a-109">onResultOneOp : 'U => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab69a-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="ab69a-110">oneArg : 'U</span><span class="sxs-lookup"><span data-stu-id="ab69a-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ab69a-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab69a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ab69a-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ab69a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab69a-113">Peut</span><span class="sxs-lookup"><span data-stu-id="ab69a-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="ab69a-114">'U</span><span class="sxs-lookup"><span data-stu-id="ab69a-114">'U</span></span>

