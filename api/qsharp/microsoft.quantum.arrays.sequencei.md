---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Séquencei, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705795"
---
# <a name="sequencei-function"></a><span data-ttu-id="ea80e-102">Séquencei, fonction</span><span class="sxs-lookup"><span data-stu-id="ea80e-102">SequenceI function</span></span>

<span data-ttu-id="ea80e-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ea80e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ea80e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea80e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea80e-105">Obtient un tableau d’entiers dans un intervalle donné.</span><span class="sxs-lookup"><span data-stu-id="ea80e-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="ea80e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ea80e-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="ea80e-107">à partir de : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea80e-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea80e-108">Index de début inclusif de l’intervalle.</span><span class="sxs-lookup"><span data-stu-id="ea80e-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="ea80e-109">à : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea80e-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea80e-110">Index de fin inclusif de l’intervalle qui n’est pas inférieur à `from` .</span><span class="sxs-lookup"><span data-stu-id="ea80e-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="ea80e-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ea80e-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ea80e-112">Tableau contenant la séquence de nombres `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="ea80e-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>