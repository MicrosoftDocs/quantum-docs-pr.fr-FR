---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857985"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="fa6d6-102">_IdentityTimeDependentGeneratorSystem fonction)</span><span class="sxs-lookup"><span data-stu-id="fa6d6-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="fa6d6-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fa6d6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fa6d6-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa6d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa6d6-105">Retourne un système de générateur conforme à la valeur de la propriété Hamilton `H(s) = 0` , où `s` est un paramètre de planification.</span><span class="sxs-lookup"><span data-stu-id="fa6d6-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="fa6d6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fa6d6-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="fa6d6-107">planification : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa6d6-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fa6d6-108">Cette entrée est ignorée et est définie pour une cohérence avec le <xref:microsoft.quantum.canon.timedependentgeneratorsystem> type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fa6d6-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="fa6d6-109">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="fa6d6-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="fa6d6-110">Un système de générateur représentant l’évolution sous la $H de la Hamilton (s) = $0 pour tous les $s $.</span><span class="sxs-lookup"><span data-stu-id="fa6d6-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>