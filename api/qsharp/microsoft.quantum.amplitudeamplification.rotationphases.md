---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Type défini par l’utilisateur RotationPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191361"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="f5b8a-102">Type défini par l’utilisateur RotationPhases</span><span class="sxs-lookup"><span data-stu-id="f5b8a-102">RotationPhases user defined type</span></span>

<span data-ttu-id="f5b8a-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="f5b8a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="f5b8a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5b8a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5b8a-105">Phases pour une séquence de rotations à qubit unique dans l’amplification d’amplitude.</span><span class="sxs-lookup"><span data-stu-id="f5b8a-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="f5b8a-106">Notes</span><span class="sxs-lookup"><span data-stu-id="f5b8a-106">Remarks</span></span>

<span data-ttu-id="f5b8a-107">Le premier paramètre est un tableau de phases pour les réflexions, exprimé sous la forme d’un produit de rotations à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="f5b8a-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="f5b8a-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="f5b8a-108">[ G.H.</span></span> <span data-ttu-id="f5b8a-109">Low, I. L.</span><span class="sxs-lookup"><span data-stu-id="f5b8a-109">Low, I. L.</span></span> <span data-ttu-id="f5b8a-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="f5b8a-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>