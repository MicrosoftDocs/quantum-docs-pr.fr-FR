---
uid: Microsoft.Quantum.Canon.RepeatC
title: Opération RepeatC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 8dc178374bdc9f8bf9f8aed57b9ae9a56995dec6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703861"
---
# <a name="repeatc-operation"></a><span data-ttu-id="1cfa8-102">Opération RepeatC</span><span class="sxs-lookup"><span data-stu-id="1cfa8-102">RepeatC operation</span></span>

<span data-ttu-id="1cfa8-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1cfa8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1cfa8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1cfa8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1cfa8-105">Répète une opération un nombre de fois donné.</span><span class="sxs-lookup"><span data-stu-id="1cfa8-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="1cfa8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1cfa8-106">Input</span></span>

### <a name="op--tinput--unit-ctl"></a><span data-ttu-id="1cfa8-107">OP : 'TInput => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1cfa8-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="1cfa8-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="1cfa8-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="1cfa8-109">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1cfa8-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1cfa8-110">Nombre d’appels de `op` .</span><span class="sxs-lookup"><span data-stu-id="1cfa8-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="1cfa8-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="1cfa8-111">input : 'TInput</span></span>

<span data-ttu-id="1cfa8-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="1cfa8-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1cfa8-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1cfa8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1cfa8-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1cfa8-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="1cfa8-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="1cfa8-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="1cfa8-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1cfa8-116">See Also</span></span>

- [<span data-ttu-id="1cfa8-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="1cfa8-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="1cfa8-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="1cfa8-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="1cfa8-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="1cfa8-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="1cfa8-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="1cfa8-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)