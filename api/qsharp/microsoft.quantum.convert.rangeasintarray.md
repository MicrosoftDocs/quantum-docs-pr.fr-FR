---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214005"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="ec7df-102">RangeAsIntArray fonction)</span><span class="sxs-lookup"><span data-stu-id="ec7df-102">RangeAsIntArray function</span></span>

<span data-ttu-id="ec7df-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ec7df-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ec7df-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec7df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec7df-105">Crée un tableau `arr` d’entiers énumérés par Start.. étape.. effet.</span><span class="sxs-lookup"><span data-stu-id="ec7df-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="ec7df-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ec7df-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="ec7df-107">plage : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ec7df-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="ec7df-108">`Range`De valeurs `start..step..end` à convertir en tableau.</span><span class="sxs-lookup"><span data-stu-id="ec7df-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="ec7df-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ec7df-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ec7df-110">Nouveau tableau d’entiers correspondant aux valeurs itérées par `range` .</span><span class="sxs-lookup"><span data-stu-id="ec7df-110">A new array of integers corresponding to values iterated over by `range`.</span></span>