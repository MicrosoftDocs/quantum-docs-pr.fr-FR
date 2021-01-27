---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Opération DrawMany
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846204"
---
# <a name="drawmany-operation"></a><span data-ttu-id="6679b-102">Opération DrawMany</span><span class="sxs-lookup"><span data-stu-id="6679b-102">DrawMany operation</span></span>

<span data-ttu-id="6679b-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6679b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6679b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6679b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6679b-105">Répète une opération pour un nombre donné d’échantillons, en collectant ses sorties dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="6679b-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="6679b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6679b-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="6679b-107">OP : 'TInput => 'TOutput</span><span class="sxs-lookup"><span data-stu-id="6679b-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="6679b-108">Opération à appeler à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="6679b-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="6679b-109">nSamples : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6679b-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6679b-110">Nombre d’exemples d’appels `op` à collecter.</span><span class="sxs-lookup"><span data-stu-id="6679b-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="6679b-111">entrée : 'TInput</span><span class="sxs-lookup"><span data-stu-id="6679b-111">input : 'TInput</span></span>

<span data-ttu-id="6679b-112">Entrée à passer à `op` .</span><span class="sxs-lookup"><span data-stu-id="6679b-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="6679b-113">Sortie : 'TOutput []</span><span class="sxs-lookup"><span data-stu-id="6679b-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6679b-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6679b-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="6679b-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="6679b-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="6679b-116">«TOutput</span><span class="sxs-lookup"><span data-stu-id="6679b-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="6679b-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="6679b-117">Example</span></span>

<span data-ttu-id="6679b-118">L’exemple suivant illustre un entier, étant donné une opération qui échantillonne un seul bit à la fois.</span><span class="sxs-lookup"><span data-stu-id="6679b-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="6679b-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6679b-119">See Also</span></span>

- [<span data-ttu-id="6679b-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="6679b-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)