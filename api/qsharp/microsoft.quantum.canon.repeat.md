---
uid: Microsoft.Quantum.Canon.Repeat
title: Répéter l’opération
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: cd572e5e082df94d762a0869ad2c1923fb71fd3d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205590"
---
# <a name="repeat-operation"></a><span data-ttu-id="947a6-102">Répéter l’opération</span><span class="sxs-lookup"><span data-stu-id="947a6-102">Repeat operation</span></span>

<span data-ttu-id="947a6-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="947a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="947a6-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="947a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="947a6-105">Répète une opération un nombre de fois donné.</span><span class="sxs-lookup"><span data-stu-id="947a6-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="947a6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="947a6-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="947a6-107">OP : 'TInput => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="947a6-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="947a6-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="947a6-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="947a6-109">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="947a6-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="947a6-110">Nombre d’appels de `op` .</span><span class="sxs-lookup"><span data-stu-id="947a6-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="947a6-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="947a6-111">input : 'TInput</span></span>

<span data-ttu-id="947a6-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="947a6-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="947a6-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="947a6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="947a6-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="947a6-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="947a6-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="947a6-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="947a6-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="947a6-116">See Also</span></span>

- [<span data-ttu-id="947a6-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="947a6-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="947a6-118">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="947a6-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="947a6-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="947a6-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="947a6-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="947a6-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)