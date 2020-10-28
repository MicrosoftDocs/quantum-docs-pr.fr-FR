---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Type défini par l’utilisateur GeneratorIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708609"
---
# <a name="generatorindex-user-defined-type"></a>Type défini par l’utilisateur GeneratorIndex

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Représente un terme primitif unique dans le jeu de tous les générateurs dynamiques, par exemple les opérateurs Hermitian, pour lesquels il existe un mappage de ce générateur à l’évolution temporelle par ce générateur, via `EvolutionSet` .

Le premier élément (int [], double []) est un index qui est un terme unique, par exemple, la chaîne Pauli XXY avec le coefficient 0,5 est indexée par ([1, 1, 2], [0,5]). Sinon, Hamiltonians paramétré par une variable continue, telle que X cos φ + Y Sin φ, peut être représenté par l’instance ([], [φ]). Le deuxième élément indexe le sous-système sur lequel le générateur agit.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a>Notes

> [!WARNING]
> L’interprétation d’un `GeneratorIndex` n’est pas définie, à l’exception de la référence à un ensemble spécifique de générateurs.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. simulation. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. Quantum. simulation. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)