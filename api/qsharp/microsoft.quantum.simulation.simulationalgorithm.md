---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Type défini par l’utilisateur SimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 9127a936bbf7a212e712645eabdf49fefc7a97d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709323"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="1c3d0-102">Type défini par l’utilisateur SimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="1c3d0-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="1c3d0-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1c3d0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1c3d0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c3d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c3d0-105">Représente un algorithme de simulation indépendant du temps.</span><span class="sxs-lookup"><span data-stu-id="1c3d0-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="1c3d0-106">Une technique de simulation indépendante du temps convertit un <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="1c3d0-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="1c3d0-107">à l’évolution de l’heure unitaire pour un intervalle de temps donné.</span><span class="sxs-lookup"><span data-stu-id="1c3d0-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

