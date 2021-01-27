---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845859"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="18f64-102">FixedPointReflectionPhases fonction)</span><span class="sxs-lookup"><span data-stu-id="18f64-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="18f64-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="18f64-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="18f64-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18f64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18f64-105">Calcule les phases de réflexion partielle pour l’amplification de l’amplitude à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="18f64-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="18f64-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="18f64-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="18f64-107">nQueries : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="18f64-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="18f64-108">Nombre de requêtes à la préparation de l’État Oracle.</span><span class="sxs-lookup"><span data-stu-id="18f64-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="18f64-109">Doit être un entier impair.</span><span class="sxs-lookup"><span data-stu-id="18f64-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="18f64-110">successMin : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="18f64-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="18f64-111">Probabilité de réussite minimale cible.</span><span class="sxs-lookup"><span data-stu-id="18f64-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="18f64-112">Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="18f64-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="18f64-113">Tableau de phases qui peut être utilisé dans l’implémentation de l’algorithme Quantum d’amplification à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="18f64-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="18f64-114">Références</span><span class="sxs-lookup"><span data-stu-id="18f64-114">References</span></span>

<span data-ttu-id="18f64-115">Nous utilisons les phases de « amplification de l’amplitude à virgule fixe avec un nombre optimal de requêtes »</span><span class="sxs-lookup"><span data-stu-id="18f64-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="18f64-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Voir aussi « méthodologie des portes Quantum composites »</span><span class="sxs-lookup"><span data-stu-id="18f64-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="18f64-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) pour les phases au `RotationPhases` format.</span><span class="sxs-lookup"><span data-stu-id="18f64-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>