---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Opération DrawMany
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706110"
---
# <a name="drawmany-operation"></a><span data-ttu-id="87da6-102">Opération DrawMany</span><span class="sxs-lookup"><span data-stu-id="87da6-102">DrawMany operation</span></span>

<span data-ttu-id="87da6-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="87da6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="87da6-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87da6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87da6-105">Répète une opération pour un nombre donné d’échantillons, en collectant ses sorties dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="87da6-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="87da6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="87da6-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="87da6-107">OP : 'TInput => 'TOutput</span><span class="sxs-lookup"><span data-stu-id="87da6-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="87da6-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="87da6-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="87da6-109">nSamples : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87da6-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87da6-110">Nombre d’exemples d’appels `op` à collecter.</span><span class="sxs-lookup"><span data-stu-id="87da6-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="87da6-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="87da6-111">input : 'TInput</span></span>

<span data-ttu-id="87da6-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="87da6-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="87da6-113">Sortie : 'TOutput []</span><span class="sxs-lookup"><span data-stu-id="87da6-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="87da6-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="87da6-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="87da6-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="87da6-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="87da6-116">«TOutput</span><span class="sxs-lookup"><span data-stu-id="87da6-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="87da6-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="87da6-117">See Also</span></span>

- [<span data-ttu-id="87da6-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="87da6-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)