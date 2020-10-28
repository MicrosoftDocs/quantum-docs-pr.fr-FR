---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707733"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="aec84-102">FixedPointReflectionPhases fonction)</span><span class="sxs-lookup"><span data-stu-id="aec84-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="aec84-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="aec84-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="aec84-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aec84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aec84-105">Calcule les phases de réflexion partielle pour l’amplification de l’amplitude à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="aec84-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="aec84-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="aec84-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="aec84-107">nQueries : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aec84-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aec84-108">Nombre de requêtes à la préparation de l’État Oracle.</span><span class="sxs-lookup"><span data-stu-id="aec84-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="aec84-109">Doit être un entier impair.</span><span class="sxs-lookup"><span data-stu-id="aec84-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="aec84-110">successMin : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aec84-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aec84-111">Probabilité de réussite minimale cible.</span><span class="sxs-lookup"><span data-stu-id="aec84-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="aec84-112">Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="aec84-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="aec84-113">Tableau de phases qui peut être utilisé dans l’implémentation de l’algorithme Quantum d’amplification à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="aec84-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="aec84-114">Références</span><span class="sxs-lookup"><span data-stu-id="aec84-114">References</span></span>

<span data-ttu-id="aec84-115">Nous utilisons les phases de « amplification de l’amplitude à virgule fixe avec un nombre optimal de requêtes »</span><span class="sxs-lookup"><span data-stu-id="aec84-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="aec84-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Voir aussi « méthodologie des portes Quantum composites »</span><span class="sxs-lookup"><span data-stu-id="aec84-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="aec84-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) pour les phases au `RotationPhases` format.</span><span class="sxs-lookup"><span data-stu-id="aec84-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>