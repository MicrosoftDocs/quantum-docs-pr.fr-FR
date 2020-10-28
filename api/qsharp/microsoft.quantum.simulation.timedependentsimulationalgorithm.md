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
# <a name="timedependentsimulationalgorithm-user-defined-type"></a>Type défini par l’utilisateur TimeDependentSimulationAlgorithm

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Représente un algorithme de simulation dépendant du temps.

Une technique de simulation dépendante du temps convertit un <xref:microsoft.quantum.simulation.evolutionschedule>
à l’évolution temporelle pour un intervalle de temps donné.

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

