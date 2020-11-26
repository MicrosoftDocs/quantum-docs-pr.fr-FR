---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229985"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="e8177-102">PurifiedMixedStateRequirements fonction)</span><span class="sxs-lookup"><span data-stu-id="e8177-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="e8177-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e8177-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e8177-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8177-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8177-105">Retourne le nombre total de qubits qui doivent être alloués afin d’appliquer l’opération retournée par @"microsoft.quantum.preparation.purifiedmixedstate" .</span><span class="sxs-lookup"><span data-stu-id="e8177-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="e8177-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e8177-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e8177-107">targetError : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8177-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8177-108">L’erreur cible $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e8177-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="e8177-109">nCoefficients : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8177-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8177-110">Nombre de coefficients à spécifier dans la préparation d’un État mixte.</span><span class="sxs-lookup"><span data-stu-id="e8177-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="e8177-111">Sortie : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="e8177-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="e8177-112">Description du nombre total de qubits requis et pour chacun des registres d’index et de nettoyage de la mémoire utilisés par la @"microsoft.quantum.preparation.purifiedmixedstate" fonction.</span><span class="sxs-lookup"><span data-stu-id="e8177-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8177-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8177-113">See Also</span></span>

- [<span data-ttu-id="e8177-114">Microsoft. Quantum. PREPARATION. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="e8177-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)