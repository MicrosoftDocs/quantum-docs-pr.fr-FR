---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Type défini par l’utilisateur RotationPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843967"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="8da38-102">Type défini par l’utilisateur RotationPhases</span><span class="sxs-lookup"><span data-stu-id="8da38-102">RotationPhases user defined type</span></span>

<span data-ttu-id="8da38-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="8da38-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="8da38-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8da38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8da38-105">Phases pour une séquence de rotations à qubit unique dans l’amplification d’amplitude.</span><span class="sxs-lookup"><span data-stu-id="8da38-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="8da38-106">Notes</span><span class="sxs-lookup"><span data-stu-id="8da38-106">Remarks</span></span>

<span data-ttu-id="8da38-107">Le premier paramètre est un tableau de phases pour les réflexions, exprimé sous la forme d’un produit de rotations à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="8da38-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="8da38-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="8da38-108">[ G.H.</span></span> <span data-ttu-id="8da38-109">Low, I. L.</span><span class="sxs-lookup"><span data-stu-id="8da38-109">Low, I. L.</span></span> <span data-ttu-id="8da38-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="8da38-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>