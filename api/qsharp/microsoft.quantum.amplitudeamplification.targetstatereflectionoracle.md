---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707676"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="fdf26-102">TargetStateReflectionOracle fonction)</span><span class="sxs-lookup"><span data-stu-id="fdf26-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="fdf26-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="fdf26-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="fdf26-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fdf26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fdf26-105">Construit un `ReflectionOracle` à propos de l’État cible marqué de manière unique par l’indicateur qubit.</span><span class="sxs-lookup"><span data-stu-id="fdf26-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="fdf26-106">L’État cible a un seul qubit défini sur 1, et tous les autres 0 : $ \ket {1} _f $.</span><span class="sxs-lookup"><span data-stu-id="fdf26-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="fdf26-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="fdf26-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="fdf26-108">idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fdf26-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fdf26-109">Index pour signaler qubit $f $ d’Oracle.</span><span class="sxs-lookup"><span data-stu-id="fdf26-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="fdf26-110">Sortie : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="fdf26-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="fdf26-111">`ReflectionOracle`Qui reflète l’État marqué par $ \ket {1} _f $.</span><span class="sxs-lookup"><span data-stu-id="fdf26-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdf26-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdf26-112">See Also</span></span>

- [<span data-ttu-id="fdf26-113">Microsoft. Quantum. Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="fdf26-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)