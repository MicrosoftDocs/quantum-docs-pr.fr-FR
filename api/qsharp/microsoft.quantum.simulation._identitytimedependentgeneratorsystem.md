---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225599"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="52cd3-102">_IdentityTimeDependentGeneratorSystem fonction)</span><span class="sxs-lookup"><span data-stu-id="52cd3-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="52cd3-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="52cd3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="52cd3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52cd3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52cd3-105">Retourne un système de générateur conforme à la valeur de la propriété Hamilton `H(s) = 0` , où `s` est un paramètre de planification.</span><span class="sxs-lookup"><span data-stu-id="52cd3-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="52cd3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="52cd3-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="52cd3-107">planification : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="52cd3-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="52cd3-108">Cette entrée est ignorée et est définie pour une cohérence avec le <xref:microsoft.quantum.canon.timedependentgeneratorsystem> type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="52cd3-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="52cd3-109">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="52cd3-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="52cd3-110">Un système de générateur représentant l’évolution sous la $H de la Hamilton (s) = $0 pour tous les $s $.</span><span class="sxs-lookup"><span data-stu-id="52cd3-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>