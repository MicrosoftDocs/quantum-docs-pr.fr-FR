---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814181"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="622e9-102">NormalDistribution fonction)</span><span class="sxs-lookup"><span data-stu-id="622e9-102">NormalDistribution function</span></span>

<span data-ttu-id="622e9-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="622e9-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="622e9-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="622e9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="622e9-105">Retourne une distribution normale avec une moyenne et une variance données.</span><span class="sxs-lookup"><span data-stu-id="622e9-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="622e9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="622e9-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="622e9-107">moyenne : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="622e9-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="622e9-108">variance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="622e9-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="622e9-109">Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="622e9-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="622e9-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="622e9-110">Example</span></span>

<span data-ttu-id="622e9-111">L’exemple suivant dessine 10 échantillons de la distribution normale avec la moyenne 2 et l’écart type 0,1 :</span><span class="sxs-lookup"><span data-stu-id="622e9-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="622e9-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="622e9-112">See Also</span></span>

- [<span data-ttu-id="622e9-113">Microsoft. Quantum. Random. StandardNormalDistribution</span><span class="sxs-lookup"><span data-stu-id="622e9-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)