---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191446"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="df911-102">FixedPointReflectionPhases fonction)</span><span class="sxs-lookup"><span data-stu-id="df911-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="df911-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="df911-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="df911-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df911-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df911-105">Calcule les phases de réflexion partielle pour l’amplification de l’amplitude à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="df911-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="df911-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="df911-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="df911-107">nQueries : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df911-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df911-108">Nombre de requêtes à la préparation de l’État Oracle.</span><span class="sxs-lookup"><span data-stu-id="df911-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="df911-109">Doit être un entier impair.</span><span class="sxs-lookup"><span data-stu-id="df911-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="df911-110">successMin : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df911-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df911-111">Probabilité de réussite minimale cible.</span><span class="sxs-lookup"><span data-stu-id="df911-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="df911-112">Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="df911-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="df911-113">Tableau de phases qui peut être utilisé dans l’implémentation de l’algorithme Quantum d’amplification à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="df911-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="df911-114">Références</span><span class="sxs-lookup"><span data-stu-id="df911-114">References</span></span>

<span data-ttu-id="df911-115">Nous utilisons les phases de « amplification de l’amplitude à virgule fixe avec un nombre optimal de requêtes »</span><span class="sxs-lookup"><span data-stu-id="df911-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="df911-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Voir aussi « méthodologie des portes Quantum composites »</span><span class="sxs-lookup"><span data-stu-id="df911-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="df911-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) pour les phases au `RotationPhases` format.</span><span class="sxs-lookup"><span data-stu-id="df911-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>