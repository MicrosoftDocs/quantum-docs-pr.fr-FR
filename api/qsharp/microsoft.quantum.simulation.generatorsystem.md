---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Type défini par l’utilisateur GeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708891"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="d1a76-102">Type défini par l’utilisateur GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="d1a76-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="d1a76-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d1a76-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d1a76-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1a76-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1a76-105">Représente une collection de `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="d1a76-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="d1a76-106">Nous effectuons une itération sur cette collection à l’aide d’un entier à index unique, et la taille de la collection est supposée être connue.</span><span class="sxs-lookup"><span data-stu-id="d1a76-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="d1a76-107">Notes</span><span class="sxs-lookup"><span data-stu-id="d1a76-107">Remarks</span></span>

<span data-ttu-id="d1a76-108">Les instances de `GeneratorSystem` peuvent être définies facilement à l’aide de la <xref:microsoft.quantum.arrays.lookupfunction> fonction.</span><span class="sxs-lookup"><span data-stu-id="d1a76-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1a76-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1a76-109">See Also</span></span>

- [<span data-ttu-id="d1a76-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="d1a76-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)