---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Type défini par l’utilisateur EvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701743"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="48aa1-102">Type défini par l’utilisateur EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="48aa1-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="48aa1-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="48aa1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="48aa1-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48aa1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48aa1-105">Représente un ensemble de portes qui peuvent être facilement implémentées et utilisées pour implémenter des algorithmes de simulation.</span><span class="sxs-lookup"><span data-stu-id="48aa1-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="48aa1-106">Les éléments du jeu sont indexés par un  <xref:microsoft.quantum.simulation.generatorindex> , et chaque jeu est décrit par une fonction de `GeneratorIndex` à  <xref:microsoft.quantum.simulation.evolutionunitary> , qui sont des opérations paramétrées par un nombre réel représentant l’heure</span><span class="sxs-lookup"><span data-stu-id="48aa1-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

