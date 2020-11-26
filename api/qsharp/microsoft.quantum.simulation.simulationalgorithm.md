---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Type défini par l’utilisateur SimulationAlgorithm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 2f340492b51c97e353cc071d6d563a30a1db86d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192432"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="2c512-102">Type défini par l’utilisateur SimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="2c512-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="2c512-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2c512-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2c512-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c512-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c512-105">Représente un algorithme de simulation indépendant du temps.</span><span class="sxs-lookup"><span data-stu-id="2c512-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="2c512-106">Une technique de simulation indépendante du temps convertit un <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="2c512-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="2c512-107">à l’évolution de l’heure unitaire pour un intervalle de temps donné.</span><span class="sxs-lookup"><span data-stu-id="2c512-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

