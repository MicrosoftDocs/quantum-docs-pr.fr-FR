---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: Opération ApplyAmplitudeAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: 8fd5c3f20c5a5aaae140feaf3af02395bff77b9c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845879"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="84f83-102">Opération ApplyAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="84f83-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="84f83-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="84f83-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="84f83-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84f83-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84f83-105">Applique l’amplification d’amplitude sur un registre donné, à l’aide d’un ensemble donné de phases et d’Oracle pour refléter les États initiaux et finaux.</span><span class="sxs-lookup"><span data-stu-id="84f83-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="84f83-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="84f83-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="84f83-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="84f83-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="84f83-108">Ensemble de phases décrivant les réflexions partielles à chaque étape de l’algorithme d’amplification d’amplitude.</span><span class="sxs-lookup"><span data-stu-id="84f83-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="84f83-109">Pour obtenir un exemple, consultez @"microsoft.quantum.amplitudeamplification.standardreflectionphases".</span><span class="sxs-lookup"><span data-stu-id="84f83-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="84f83-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="84f83-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="84f83-111">Oracle qui reflète l’état initial.</span><span class="sxs-lookup"><span data-stu-id="84f83-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="84f83-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="84f83-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="84f83-113">Oracle qui reflète l’état final souhaité.</span><span class="sxs-lookup"><span data-stu-id="84f83-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="84f83-114">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="84f83-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="84f83-115">Registre sur lequel effectuer l’amplification de l’amplitude.</span><span class="sxs-lookup"><span data-stu-id="84f83-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84f83-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84f83-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

