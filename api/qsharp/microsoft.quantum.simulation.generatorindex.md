---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Type défini par l’utilisateur GeneratorIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858383"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="e528c-102">Type défini par l’utilisateur GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="e528c-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="e528c-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e528c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e528c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e528c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e528c-105">Représente un terme primitif unique dans le jeu de tous les générateurs dynamiques, par exemple les opérateurs Hermitian, pour lesquels il existe un mappage de ce générateur à l’évolution temporelle par ce générateur, via `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="e528c-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="e528c-106">Le premier élément (int [], double []) est un index qui est un terme unique, par exemple, la chaîne Pauli XXY avec le coefficient 0,5 est indexée par ([1, 1, 2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="e528c-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="e528c-107">Sinon, Hamiltonians paramétré par une variable continue, telle que X cos φ + Y Sin φ, peut être représenté par l’instance ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="e528c-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="e528c-108">Le deuxième élément indexe le sous-système sur lequel le générateur agit.</span><span class="sxs-lookup"><span data-stu-id="e528c-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a><span data-ttu-id="e528c-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="e528c-109">Example</span></span>

<span data-ttu-id="e528c-110">À l’aide de  <xref:microsoft.quantum.simulation.paulievolutionset> , l’opérateur $ \pi X_2 X_5 Y_9 $ est représenté comme suit :</span><span class="sxs-lookup"><span data-stu-id="e528c-110">Using  <xref:microsoft.quantum.simulation.paulievolutionset>, the operator $\pi X_2 X_5 Y_9$ is represented as:</span></span>

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a><span data-ttu-id="e528c-111">Notes</span><span class="sxs-lookup"><span data-stu-id="e528c-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e528c-112">L’interprétation d’un `GeneratorIndex` n’est pas définie, à l’exception de la référence à un ensemble spécifique de générateurs.</span><span class="sxs-lookup"><span data-stu-id="e528c-112">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="e528c-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e528c-113">See Also</span></span>

- [<span data-ttu-id="e528c-114">Microsoft. Quantum. simulation. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="e528c-114">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="e528c-115">Microsoft. Quantum. simulation. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="e528c-115">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)