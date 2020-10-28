---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702922"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="393bc-102">RangeAsIntArray fonction)</span><span class="sxs-lookup"><span data-stu-id="393bc-102">RangeAsIntArray function</span></span>

<span data-ttu-id="393bc-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="393bc-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="393bc-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="393bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="393bc-105">Crée un tableau `arr` d’entiers énumérés par Start.. étape.. effet.</span><span class="sxs-lookup"><span data-stu-id="393bc-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="393bc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="393bc-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="393bc-107">plage : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="393bc-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="393bc-108">`Range`De valeurs `start..step..end` à convertir en tableau.</span><span class="sxs-lookup"><span data-stu-id="393bc-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="393bc-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="393bc-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="393bc-110">Nouveau tableau d’entiers correspondant aux valeurs itérées par `range` .</span><span class="sxs-lookup"><span data-stu-id="393bc-110">A new array of integers corresponding to values iterated over by `range`.</span></span>