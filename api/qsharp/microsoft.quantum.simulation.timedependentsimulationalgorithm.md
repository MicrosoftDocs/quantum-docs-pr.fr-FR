---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: Type défini par l’utilisateur TimeDependentSimulationAlgorithm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709401"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="d2c40-102">Type défini par l’utilisateur TimeDependentSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="d2c40-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="d2c40-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d2c40-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d2c40-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2c40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2c40-105">Représente un algorithme de simulation dépendant du temps.</span><span class="sxs-lookup"><span data-stu-id="d2c40-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="d2c40-106">Une technique de simulation dépendante du temps convertit un <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="d2c40-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="d2c40-107">à l’évolution temporelle pour un intervalle de temps donné.</span><span class="sxs-lookup"><span data-stu-id="d2c40-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

