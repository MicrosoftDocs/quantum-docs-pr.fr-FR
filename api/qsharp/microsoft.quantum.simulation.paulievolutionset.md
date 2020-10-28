---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707814"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="465d8-102">PauliEvolutionSet fonction)</span><span class="sxs-lookup"><span data-stu-id="465d8-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="465d8-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="465d8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="465d8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="465d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="465d8-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de Pauli.</span><span class="sxs-lookup"><span data-stu-id="465d8-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="465d8-106">Sortie : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="465d8-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="465d8-107">`EvolutionSet`Qui mappe un `GeneratorIndex` pour la base Pauli à un’EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="465d8-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="465d8-108">Notes</span><span class="sxs-lookup"><span data-stu-id="465d8-108">Remarks</span></span>

<span data-ttu-id="465d8-109">Cela est obtenu par une application partielle de <xref:microsoft.quantum.simulation.paulievolutionfunction> .</span><span class="sxs-lookup"><span data-stu-id="465d8-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>