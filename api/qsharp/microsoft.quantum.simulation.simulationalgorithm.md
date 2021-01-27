---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Type défini par l’utilisateur SimulationAlgorithm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: d7b233ee76d79072f59ecfd001245848cb780eec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851044"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="e2402-102">Type défini par l’utilisateur SimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="e2402-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="e2402-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e2402-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e2402-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2402-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2402-105">Représente un algorithme de simulation indépendant du temps.</span><span class="sxs-lookup"><span data-stu-id="e2402-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="e2402-106">Une technique de simulation indépendante du temps convertit un <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="e2402-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="e2402-107">à l’évolution de l’heure unitaire pour un intervalle de temps donné.</span><span class="sxs-lookup"><span data-stu-id="e2402-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

