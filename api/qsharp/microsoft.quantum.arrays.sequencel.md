---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Fonction Sequence
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705782"
---
# <a name="sequencel-function"></a><span data-ttu-id="a06b3-102">Fonction Sequence</span><span class="sxs-lookup"><span data-stu-id="a06b3-102">SequenceL function</span></span>

<span data-ttu-id="a06b3-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a06b3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a06b3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a06b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a06b3-105">Obtient un tableau d’entiers dans un intervalle donné.</span><span class="sxs-lookup"><span data-stu-id="a06b3-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="a06b3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a06b3-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="a06b3-107">de : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a06b3-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a06b3-108">Index de début inclusif de l’intervalle.</span><span class="sxs-lookup"><span data-stu-id="a06b3-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="a06b3-109">à : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a06b3-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a06b3-110">Index de fin inclusif de l’intervalle qui n’est pas inférieur à `from` .</span><span class="sxs-lookup"><span data-stu-id="a06b3-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="a06b3-111">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="a06b3-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="a06b3-112">Tableau contenant la séquence de nombres `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="a06b3-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a06b3-113">Notes</span><span class="sxs-lookup"><span data-stu-id="a06b3-113">Remarks</span></span>

<span data-ttu-id="a06b3-114">La différence entre `from` et `to` doit tenir dans une `Int` valeur.</span><span class="sxs-lookup"><span data-stu-id="a06b3-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>