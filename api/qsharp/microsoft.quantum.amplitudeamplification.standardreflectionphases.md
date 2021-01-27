---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843919"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="46602-102">StandardReflectionPhases fonction)</span><span class="sxs-lookup"><span data-stu-id="46602-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="46602-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="46602-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="46602-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46602-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46602-105">Calcule les phases de réflexion partielle pour l’amplification de l’amplitude standard.</span><span class="sxs-lookup"><span data-stu-id="46602-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="46602-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="46602-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="46602-107">nIterations : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46602-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46602-108">Nombre d’itérations d’amplification d’amplitude pour générer des phases de réflexion partielles pour.</span><span class="sxs-lookup"><span data-stu-id="46602-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="46602-109">Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="46602-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="46602-110">Opération qui implémente des phases spécifiées en tant que réflexions partielles</span><span class="sxs-lookup"><span data-stu-id="46602-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="46602-111">Notes</span><span class="sxs-lookup"><span data-stu-id="46602-111">Remarks</span></span>

<span data-ttu-id="46602-112">Toutes les phases sont de $ \pi $, à l’exception de la première réflexion à propos de l’état de démarrage et de la dernière réflexion sur l’État cible, qui sont $0 $.</span><span class="sxs-lookup"><span data-stu-id="46602-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>