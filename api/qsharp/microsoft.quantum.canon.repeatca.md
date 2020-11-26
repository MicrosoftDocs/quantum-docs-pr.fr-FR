---
uid: Microsoft.Quantum.Canon.RepeatCA
title: Opération RepeatCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 24606486b3d5703065a7c7f62d3bbc7e3d07615f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205403"
---
# <a name="repeatca-operation"></a><span data-ttu-id="17498-102">Opération RepeatCA</span><span class="sxs-lookup"><span data-stu-id="17498-102">RepeatCA operation</span></span>

<span data-ttu-id="17498-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17498-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17498-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17498-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17498-105">Répète une opération un nombre de fois donné.</span><span class="sxs-lookup"><span data-stu-id="17498-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="17498-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="17498-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="17498-107">OP : 'TInput => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="17498-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="17498-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="17498-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="17498-109">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17498-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="17498-110">Nombre d’appels de `op` .</span><span class="sxs-lookup"><span data-stu-id="17498-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="17498-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="17498-111">input : 'TInput</span></span>

<span data-ttu-id="17498-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="17498-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17498-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17498-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="17498-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="17498-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="17498-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="17498-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="17498-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17498-116">See Also</span></span>

- [<span data-ttu-id="17498-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="17498-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="17498-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="17498-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="17498-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="17498-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="17498-120">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="17498-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)