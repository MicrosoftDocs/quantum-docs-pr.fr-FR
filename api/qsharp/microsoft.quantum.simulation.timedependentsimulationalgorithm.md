---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: Type défini par l’utilisateur TimeDependentSimulationAlgorithm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: b495a9fd96c78872f84e8f8183105f6290f70655
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192517"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="8d47f-102">Type défini par l’utilisateur TimeDependentSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="8d47f-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="8d47f-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8d47f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8d47f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d47f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d47f-105">Représente un algorithme de simulation dépendant du temps.</span><span class="sxs-lookup"><span data-stu-id="8d47f-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="8d47f-106">Une technique de simulation dépendante du temps convertit un <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="8d47f-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="8d47f-107">à l’évolution temporelle pour un intervalle de temps donné.</span><span class="sxs-lookup"><span data-stu-id="8d47f-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

