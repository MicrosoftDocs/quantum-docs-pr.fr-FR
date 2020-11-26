---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Type défini par l’utilisateur GeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225225"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="daf70-102">Type défini par l’utilisateur GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="daf70-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="daf70-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="daf70-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="daf70-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="daf70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="daf70-105">Représente une collection de `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="daf70-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="daf70-106">Nous effectuons une itération sur cette collection à l’aide d’un entier à index unique, et la taille de la collection est supposée être connue.</span><span class="sxs-lookup"><span data-stu-id="daf70-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="daf70-107">Notes</span><span class="sxs-lookup"><span data-stu-id="daf70-107">Remarks</span></span>

<span data-ttu-id="daf70-108">Les instances de `GeneratorSystem` peuvent être définies facilement à l’aide de la <xref:microsoft.quantum.arrays.lookupfunction> fonction.</span><span class="sxs-lookup"><span data-stu-id="daf70-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="daf70-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="daf70-109">See Also</span></span>

- [<span data-ttu-id="daf70-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="daf70-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)