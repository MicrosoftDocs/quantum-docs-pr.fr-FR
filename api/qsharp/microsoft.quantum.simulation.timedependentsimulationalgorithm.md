---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: Type défini par l’utilisateur TimeDependentSimulationAlgorithm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 4f393c958e686f2ded3bf3372ff9fd52b2a363cd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854136"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="7bd18-102">Type défini par l’utilisateur TimeDependentSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="7bd18-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="7bd18-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7bd18-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7bd18-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7bd18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7bd18-105">Représente un algorithme de simulation dépendant du temps.</span><span class="sxs-lookup"><span data-stu-id="7bd18-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="7bd18-106">Une technique de simulation dépendante du temps convertit un <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="7bd18-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="7bd18-107">à l’évolution temporelle pour un intervalle de temps donné.</span><span class="sxs-lookup"><span data-stu-id="7bd18-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

