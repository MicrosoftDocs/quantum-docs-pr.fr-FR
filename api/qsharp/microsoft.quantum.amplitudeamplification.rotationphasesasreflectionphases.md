---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191191"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="8f542-102">RotationPhasesAsReflectionPhases fonction)</span><span class="sxs-lookup"><span data-stu-id="8f542-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="8f542-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="8f542-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="8f542-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f542-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f542-105">Convertit les phases spécifiées sous forme de rotations de qubit simple en phases spécifiées comme réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="8f542-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="8f542-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="8f542-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="8f542-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="8f542-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="8f542-108">Tableau de rotations à qubit unique à convertir en réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="8f542-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="8f542-109">Sortie : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="8f542-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="8f542-110">Opération qui implémente des phases spécifiées en tant que réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="8f542-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="8f542-111">Références</span><span class="sxs-lookup"><span data-stu-id="8f542-111">References</span></span>

<span data-ttu-id="8f542-112">Nous utilisons la Convention dans</span><span class="sxs-lookup"><span data-stu-id="8f542-112">We use the convention in</span></span>

- <span data-ttu-id="8f542-113">[ *G.H. Low, I. L. Chuang*](https://arxiv.org/abs/1707.05391) pour la liaison des phases de rotation simple qubit aux phases d’opérateur de réflexion.</span><span class="sxs-lookup"><span data-stu-id="8f542-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>