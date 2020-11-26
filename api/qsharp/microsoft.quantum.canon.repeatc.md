---
uid: Microsoft.Quantum.Canon.RepeatC
title: Opération RepeatC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 30fd172584b36601c4b81deff494cf55964518f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205437"
---
# <a name="repeatc-operation"></a><span data-ttu-id="d4249-102">Opération RepeatC</span><span class="sxs-lookup"><span data-stu-id="d4249-102">RepeatC operation</span></span>

<span data-ttu-id="d4249-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4249-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4249-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4249-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4249-105">Répète une opération un nombre de fois donné.</span><span class="sxs-lookup"><span data-stu-id="d4249-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="d4249-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d4249-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="d4249-107">OP : 'TInput => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="d4249-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d4249-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="d4249-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="d4249-109">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4249-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4249-110">Nombre d’appels de `op` .</span><span class="sxs-lookup"><span data-stu-id="d4249-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="d4249-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="d4249-111">input : 'TInput</span></span>

<span data-ttu-id="d4249-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="d4249-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4249-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4249-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d4249-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d4249-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="d4249-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="d4249-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="d4249-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4249-116">See Also</span></span>

- [<span data-ttu-id="d4249-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="d4249-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="d4249-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="d4249-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="d4249-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="d4249-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="d4249-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="d4249-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)