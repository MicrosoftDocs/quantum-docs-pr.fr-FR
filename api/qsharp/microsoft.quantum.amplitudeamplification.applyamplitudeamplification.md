---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: Opération ApplyAmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707763"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="efb40-102">Opération ApplyAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="efb40-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="efb40-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="efb40-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="efb40-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="efb40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="efb40-105">Applique l’amplification d’amplitude sur un registre donné, à l’aide d’un ensemble donné de phases et d’Oracle pour refléter les États initiaux et finaux.</span><span class="sxs-lookup"><span data-stu-id="efb40-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="efb40-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="efb40-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="efb40-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="efb40-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="efb40-108">Ensemble de phases décrivant les réflexions partielles à chaque étape de l’algorithme d’amplification d’amplitude.</span><span class="sxs-lookup"><span data-stu-id="efb40-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="efb40-109">Pour obtenir un exemple, consultez @"microsoft.quantum.amplitudeamplification.standardreflectionphases".</span><span class="sxs-lookup"><span data-stu-id="efb40-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="efb40-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="efb40-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="efb40-111">Oracle qui reflète l’état initial.</span><span class="sxs-lookup"><span data-stu-id="efb40-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="efb40-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="efb40-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="efb40-113">Oracle qui reflète l’état final souhaité.</span><span class="sxs-lookup"><span data-stu-id="efb40-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="efb40-114">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="efb40-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="efb40-115">Registre sur lequel effectuer l’amplification de l’amplitude.</span><span class="sxs-lookup"><span data-stu-id="efb40-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="efb40-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="efb40-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

