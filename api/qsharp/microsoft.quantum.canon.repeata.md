---
uid: Microsoft.Quantum.Canon.RepeatA
title: Opération de répétition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703864"
---
# <a name="repeata-operation"></a><span data-ttu-id="34a8e-102">Opération de répétition</span><span class="sxs-lookup"><span data-stu-id="34a8e-102">RepeatA operation</span></span>

<span data-ttu-id="34a8e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="34a8e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="34a8e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34a8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34a8e-105">Répète une opération un nombre de fois donné.</span><span class="sxs-lookup"><span data-stu-id="34a8e-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="34a8e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="34a8e-106">Input</span></span>

### <a name="op--tinput--unit-adj"></a><span data-ttu-id="34a8e-107">OP : 'TInput => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34a8e-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="34a8e-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="34a8e-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="34a8e-109">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34a8e-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34a8e-110">Nombre d’appels de `op` .</span><span class="sxs-lookup"><span data-stu-id="34a8e-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="34a8e-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="34a8e-111">input : 'TInput</span></span>

<span data-ttu-id="34a8e-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="34a8e-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="34a8e-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34a8e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="34a8e-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="34a8e-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="34a8e-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="34a8e-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="34a8e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34a8e-116">See Also</span></span>

- [<span data-ttu-id="34a8e-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="34a8e-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="34a8e-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="34a8e-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="34a8e-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="34a8e-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="34a8e-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="34a8e-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)