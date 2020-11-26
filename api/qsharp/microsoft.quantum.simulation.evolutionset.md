---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Type défini par l’utilisateur EvolutionSet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: ee8f3c0716f035dcb0c4fad557092fbf8dd3c356
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229407"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="584e2-102">Type défini par l’utilisateur EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="584e2-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="584e2-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="584e2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="584e2-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="584e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="584e2-105">Représente un ensemble de portes qui peuvent être facilement implémentées et utilisées pour implémenter des algorithmes de simulation.</span><span class="sxs-lookup"><span data-stu-id="584e2-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="584e2-106">Les éléments du jeu sont indexés par un  <xref:microsoft.quantum.simulation.generatorindex> , et chaque jeu est décrit par une fonction de `GeneratorIndex` à  <xref:microsoft.quantum.simulation.evolutionunitary> , qui sont des opérations paramétrées par un nombre réel représentant l’heure</span><span class="sxs-lookup"><span data-stu-id="584e2-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

