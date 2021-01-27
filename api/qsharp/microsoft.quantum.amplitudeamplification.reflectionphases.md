---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Type défini par l’utilisateur ReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847178"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="fc828-102">Type défini par l’utilisateur ReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="fc828-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="fc828-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="fc828-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="fc828-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc828-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc828-105">Phases pour une séquence de réflexions partielles dans l’amplification d’amplitude.</span><span class="sxs-lookup"><span data-stu-id="fc828-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="fc828-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="fc828-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="fc828-107">AboutStart : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="fc828-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="fc828-108">Tableau de phases pour la réflexion à propos de l’état de démarrage.</span><span class="sxs-lookup"><span data-stu-id="fc828-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="fc828-109">AboutTarget : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="fc828-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="fc828-110">Tableau de phases pour la réflexion sur l’État cible.</span><span class="sxs-lookup"><span data-stu-id="fc828-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc828-111">Notes</span><span class="sxs-lookup"><span data-stu-id="fc828-111">Remarks</span></span>

<span data-ttu-id="fc828-112">Les deux tableaux doivent être de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="fc828-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="fc828-113">Notez que dans de nombreux cas, la première phase à propos de l’état de démarrage et de la dernière phase de l’État cible introduit une phase de décalage global et peut être définie sur $0 $.</span><span class="sxs-lookup"><span data-stu-id="fc828-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>