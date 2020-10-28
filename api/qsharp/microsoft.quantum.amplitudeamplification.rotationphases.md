---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Type défini par l’utilisateur RotationPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707694"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="27633-102">Type défini par l’utilisateur RotationPhases</span><span class="sxs-lookup"><span data-stu-id="27633-102">RotationPhases user defined type</span></span>

<span data-ttu-id="27633-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="27633-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="27633-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27633-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27633-105">Phases pour une séquence de rotations à qubit unique dans l’amplification d’amplitude.</span><span class="sxs-lookup"><span data-stu-id="27633-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="27633-106">Notes</span><span class="sxs-lookup"><span data-stu-id="27633-106">Remarks</span></span>

<span data-ttu-id="27633-107">Le premier paramètre est un tableau de phases pour les réflexions, exprimé sous la forme d’un produit de rotations à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="27633-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="27633-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="27633-108">[ G.H.</span></span> <span data-ttu-id="27633-109">Low, I. L.</span><span class="sxs-lookup"><span data-stu-id="27633-109">Low, I. L.</span></span> <span data-ttu-id="27633-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="27633-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>