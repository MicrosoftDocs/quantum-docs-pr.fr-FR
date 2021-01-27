---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Type défini par l’utilisateur GeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858411"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="2dc8f-102">Type défini par l’utilisateur GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="2dc8f-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="2dc8f-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2dc8f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2dc8f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2dc8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2dc8f-105">Représente une collection de `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="2dc8f-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="2dc8f-106">Nous effectuons une itération sur cette collection à l’aide d’un entier à index unique, et la taille de la collection est supposée être connue.</span><span class="sxs-lookup"><span data-stu-id="2dc8f-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="2dc8f-107">Notes</span><span class="sxs-lookup"><span data-stu-id="2dc8f-107">Remarks</span></span>

<span data-ttu-id="2dc8f-108">Les instances de `GeneratorSystem` peuvent être définies facilement à l’aide de la <xref:microsoft.quantum.arrays.lookupfunction> fonction.</span><span class="sxs-lookup"><span data-stu-id="2dc8f-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dc8f-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2dc8f-109">See Also</span></span>

- [<span data-ttu-id="2dc8f-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="2dc8f-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)