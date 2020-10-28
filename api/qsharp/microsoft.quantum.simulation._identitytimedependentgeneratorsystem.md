---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701776"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="dc820-102">_IdentityTimeDependentGeneratorSystem fonction)</span><span class="sxs-lookup"><span data-stu-id="dc820-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="dc820-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dc820-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dc820-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc820-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc820-105">Retourne un système de générateur conforme à la valeur de la propriété Hamilton `H(s) = 0` , où `s` est un paramètre de planification.</span><span class="sxs-lookup"><span data-stu-id="dc820-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="dc820-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="dc820-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="dc820-107">planification : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dc820-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dc820-108">Cette entrée est ignorée et est définie pour une cohérence avec le <xref:microsoft.quantum.canon.timedependentgeneratorsystem> type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dc820-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="dc820-109">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="dc820-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="dc820-110">Un système de générateur représentant l’évolution sous la $H de la Hamilton (s) = $0 pour tous les $s $.</span><span class="sxs-lookup"><span data-stu-id="dc820-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>