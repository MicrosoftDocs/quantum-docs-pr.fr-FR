---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701884"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="ed551-102">TransformedContinuousDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="ed551-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="ed551-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ed551-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ed551-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed551-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed551-105">À partir d’une distribution continue, retourne une nouvelle distribution qui transforme l’original par une fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="ed551-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="ed551-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ed551-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="ed551-107">transformation : [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ed551-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ed551-108">Fonction qui transforme les variates de la distribution d’origine en distribution transformée.</span><span class="sxs-lookup"><span data-stu-id="ed551-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="ed551-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="ed551-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="ed551-110">Distribution d’origine à transformer.</span><span class="sxs-lookup"><span data-stu-id="ed551-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="ed551-111">Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="ed551-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="ed551-112">Nouvelle distribution liée à `distribution` par la transformation donnée par `transform` .</span><span class="sxs-lookup"><span data-stu-id="ed551-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>