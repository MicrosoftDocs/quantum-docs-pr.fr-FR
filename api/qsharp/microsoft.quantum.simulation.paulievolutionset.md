---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 961c95e6787b69e35ca531fa36164cc988ad660d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847959"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="875ef-102">PauliEvolutionSet fonction)</span><span class="sxs-lookup"><span data-stu-id="875ef-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="875ef-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="875ef-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="875ef-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="875ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="875ef-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de Pauli.</span><span class="sxs-lookup"><span data-stu-id="875ef-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="875ef-106">Sortie : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="875ef-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="875ef-107">`EvolutionSet`Qui mappe un `GeneratorIndex` pour la base Pauli à un’EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="875ef-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="875ef-108">Notes</span><span class="sxs-lookup"><span data-stu-id="875ef-108">Remarks</span></span>

<span data-ttu-id="875ef-109">Cela est obtenu par une application partielle de <xref:microsoft.quantum.simulation.paulievolutionfunction> .</span><span class="sxs-lookup"><span data-stu-id="875ef-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>