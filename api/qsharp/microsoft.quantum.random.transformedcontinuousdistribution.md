---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857770"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="9ec3a-102">TransformedContinuousDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="9ec3a-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="9ec3a-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="9ec3a-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="9ec3a-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9ec3a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9ec3a-105">À partir d’une distribution continue, retourne une nouvelle distribution qui transforme l’original par une fonction donnée.</span><span class="sxs-lookup"><span data-stu-id="9ec3a-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="9ec3a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9ec3a-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="9ec3a-107">transformation : [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9ec3a-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9ec3a-108">Fonction qui transforme les variates de la distribution d’origine en distribution transformée.</span><span class="sxs-lookup"><span data-stu-id="9ec3a-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="9ec3a-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="9ec3a-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="9ec3a-110">Distribution d’origine à transformer.</span><span class="sxs-lookup"><span data-stu-id="9ec3a-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="9ec3a-111">Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="9ec3a-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="9ec3a-112">Nouvelle distribution liée à `distribution` par la transformation donnée par `transform` .</span><span class="sxs-lookup"><span data-stu-id="9ec3a-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>

## <a name="example"></a><span data-ttu-id="9ec3a-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="9ec3a-113">Example</span></span>

<span data-ttu-id="9ec3a-114">Les deux distributions suivantes sont identiques :</span><span class="sxs-lookup"><span data-stu-id="9ec3a-114">The following two distributions are identical:</span></span>

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```