---
uid: Microsoft.Quantum.Canon.RepeatCA
title: Opération RepeatCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703858"
---
# <a name="repeatca-operation"></a><span data-ttu-id="fcf83-102">Opération RepeatCA</span><span class="sxs-lookup"><span data-stu-id="fcf83-102">RepeatCA operation</span></span>

<span data-ttu-id="fcf83-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fcf83-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fcf83-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fcf83-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fcf83-105">Répète une opération un nombre de fois donné.</span><span class="sxs-lookup"><span data-stu-id="fcf83-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="fcf83-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fcf83-106">Input</span></span>

### <a name="op--tinput--unit-adj--ctl"></a><span data-ttu-id="fcf83-107">OP : 'TInput => de l' [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="fcf83-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="fcf83-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="fcf83-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="fcf83-109">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcf83-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcf83-110">Nombre d’appels de `op` .</span><span class="sxs-lookup"><span data-stu-id="fcf83-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="fcf83-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="fcf83-111">input : 'TInput</span></span>

<span data-ttu-id="fcf83-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="fcf83-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fcf83-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fcf83-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fcf83-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="fcf83-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="fcf83-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="fcf83-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="fcf83-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcf83-116">See Also</span></span>

- [<span data-ttu-id="fcf83-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="fcf83-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="fcf83-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="fcf83-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="fcf83-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="fcf83-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="fcf83-120">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="fcf83-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)