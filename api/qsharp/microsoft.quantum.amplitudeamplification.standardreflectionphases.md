---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707679"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="96dc4-102">StandardReflectionPhases fonction)</span><span class="sxs-lookup"><span data-stu-id="96dc4-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="96dc4-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="96dc4-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="96dc4-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96dc4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96dc4-105">Calcule les phases de réflexion partielle pour l’amplification de l’amplitude standard.</span><span class="sxs-lookup"><span data-stu-id="96dc4-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="96dc4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="96dc4-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="96dc4-107">nIterations : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96dc4-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96dc4-108">Nombre d’itérations d’amplification d’amplitude pour générer des phases de réflexion partielles pour.</span><span class="sxs-lookup"><span data-stu-id="96dc4-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="96dc4-109">Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="96dc4-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="96dc4-110">Opération qui implémente des phases spécifiées en tant que réflexions partielles</span><span class="sxs-lookup"><span data-stu-id="96dc4-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="96dc4-111">Notes</span><span class="sxs-lookup"><span data-stu-id="96dc4-111">Remarks</span></span>

<span data-ttu-id="96dc4-112">Toutes les phases sont de $ \pi $, à l’exception de la première réflexion à propos de l’état de démarrage et de la dernière réflexion sur l’État cible, qui sont $0 $.</span><span class="sxs-lookup"><span data-stu-id="96dc4-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>