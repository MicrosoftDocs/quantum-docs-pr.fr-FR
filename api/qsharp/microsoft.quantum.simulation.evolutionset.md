---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Type défini par l’utilisateur EvolutionSet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856071"
---
# <a name="evolutionset-user-defined-type"></a>Type défini par l’utilisateur EvolutionSet

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente un ensemble de portes qui peuvent être facilement implémentées et utilisées pour implémenter des algorithmes de simulation.

Les éléments du jeu sont indexés par un  <xref:microsoft.quantum.simulation.generatorindex> , et chaque jeu est décrit par une fonction de `GeneratorIndex` à  <xref:microsoft.quantum.simulation.evolutionunitary> , qui sont des opérations paramétrées par un nombre réel représentant l’heure

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

