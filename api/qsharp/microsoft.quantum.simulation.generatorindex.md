---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Type défini par l’utilisateur GeneratorIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: dae23db9bee34be4aa99d96799efad64a66d7193
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229322"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="570d7-102">Type défini par l’utilisateur GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="570d7-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="570d7-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="570d7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="570d7-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="570d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="570d7-105">Représente un terme primitif unique dans le jeu de tous les générateurs dynamiques, par exemple les opérateurs Hermitian, pour lesquels il existe un mappage de ce générateur à l’évolution temporelle par ce générateur, via `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="570d7-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="570d7-106">Le premier élément (int [], double []) est un index qui est un terme unique, par exemple, la chaîne Pauli XXY avec le coefficient 0,5 est indexée par ([1, 1, 2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="570d7-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="570d7-107">Sinon, Hamiltonians paramétré par une variable continue, telle que X cos φ + Y Sin φ, peut être représenté par l’instance ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="570d7-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="570d7-108">Le deuxième élément indexe le sous-système sur lequel le générateur agit.</span><span class="sxs-lookup"><span data-stu-id="570d7-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="570d7-109">Notes</span><span class="sxs-lookup"><span data-stu-id="570d7-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="570d7-110">L’interprétation d’un `GeneratorIndex` n’est pas définie, à l’exception de la référence à un ensemble spécifique de générateurs.</span><span class="sxs-lookup"><span data-stu-id="570d7-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="570d7-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="570d7-111">See Also</span></span>

- [<span data-ttu-id="570d7-112">Microsoft. Quantum. simulation. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="570d7-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="570d7-113">Microsoft. Quantum. simulation. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="570d7-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)