---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Type défini par l’utilisateur ReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191344"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="59733-102">Type défini par l’utilisateur ReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="59733-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="59733-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="59733-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="59733-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59733-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59733-105">Phases pour une séquence de réflexions partielles dans l’amplification d’amplitude.</span><span class="sxs-lookup"><span data-stu-id="59733-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="59733-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="59733-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="59733-107">AboutStart : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="59733-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="59733-108">Tableau de phases pour la réflexion à propos de l’état de démarrage.</span><span class="sxs-lookup"><span data-stu-id="59733-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="59733-109">AboutTarget : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="59733-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="59733-110">Tableau de phases pour la réflexion sur l’État cible.</span><span class="sxs-lookup"><span data-stu-id="59733-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="59733-111">Notes</span><span class="sxs-lookup"><span data-stu-id="59733-111">Remarks</span></span>

<span data-ttu-id="59733-112">Les deux tableaux doivent être de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="59733-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="59733-113">Notez que dans de nombreux cas, la première phase à propos de l’état de démarrage et de la dernière phase de l’État cible introduit une phase de décalage global et peut être définie sur $0 $.</span><span class="sxs-lookup"><span data-stu-id="59733-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>