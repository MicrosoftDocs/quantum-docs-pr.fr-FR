---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Type défini par l’utilisateur ReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707715"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="d2ddd-102">Type défini par l’utilisateur ReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="d2ddd-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="d2ddd-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d2ddd-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d2ddd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2ddd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2ddd-105">Phases pour une séquence de réflexions partielles dans l’amplification d’amplitude.</span><span class="sxs-lookup"><span data-stu-id="d2ddd-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="d2ddd-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="d2ddd-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="d2ddd-107">AboutStart : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d2ddd-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d2ddd-108">Tableau de phases pour la réflexion à propos de l’état de démarrage.</span><span class="sxs-lookup"><span data-stu-id="d2ddd-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="d2ddd-109">AboutTarget : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d2ddd-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d2ddd-110">Tableau de phases pour la réflexion sur l’État cible.</span><span class="sxs-lookup"><span data-stu-id="d2ddd-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2ddd-111">Notes</span><span class="sxs-lookup"><span data-stu-id="d2ddd-111">Remarks</span></span>

<span data-ttu-id="d2ddd-112">Les deux tableaux doivent être de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="d2ddd-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="d2ddd-113">Notez que dans de nombreux cas, la première phase à propos de l’état de démarrage et de la dernière phase de l’État cible introduit une phase de décalage global et peut être définie sur $0 $.</span><span class="sxs-lookup"><span data-stu-id="d2ddd-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>