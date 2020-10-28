---
uid: Microsoft.Quantum.Canon.Repeat
title: Répéter l’opération
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703879"
---
# <a name="repeat-operation"></a><span data-ttu-id="6c644-102">Répéter l’opération</span><span class="sxs-lookup"><span data-stu-id="6c644-102">Repeat operation</span></span>

<span data-ttu-id="6c644-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6c644-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6c644-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c644-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c644-105">Répète une opération un nombre de fois donné.</span><span class="sxs-lookup"><span data-stu-id="6c644-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="6c644-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6c644-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="6c644-107">OP : 'TInput => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c644-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6c644-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="6c644-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="6c644-109">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c644-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6c644-110">Nombre d’appels de `op` .</span><span class="sxs-lookup"><span data-stu-id="6c644-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="6c644-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="6c644-111">input : 'TInput</span></span>

<span data-ttu-id="6c644-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="6c644-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6c644-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6c644-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6c644-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6c644-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="6c644-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="6c644-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="6c644-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c644-116">See Also</span></span>

- [<span data-ttu-id="6c644-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="6c644-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="6c644-118">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="6c644-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="6c644-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="6c644-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="6c644-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="6c644-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)