---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 2cd555882792c29cb2ed71972739505df11fbabc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225735"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a>JordanWignerOptimizedFermionEvolutionSet fonction)

Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)

Package : [Microsoft. Quantum. Research. chimie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de Pauli.

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a>Entrée

### <a name="parityqubit--qubit"></a>parityQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit qui détermine le signe de l’évolution du temps.



## <a name="output--evolutionset"></a>Sortie : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

`EvolutionSet`Qui mappe un `GeneratorIndex` pour la base JWOptimized à un’EvolutionUnitary.