---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: Type défini par l’utilisateur EvolutionSchedule
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: 345374fb8105f0f892eaef3bd2da0f0fa239c065
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814248"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="8b1b9-102">Type défini par l’utilisateur EvolutionSchedule</span><span class="sxs-lookup"><span data-stu-id="8b1b9-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="8b1b9-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8b1b9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8b1b9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b1b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b1b9-105">Représente un générateur dynamique dépendant du temps.</span><span class="sxs-lookup"><span data-stu-id="8b1b9-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="8b1b9-106">Le `Double` paramètre est une planification dans $ [0, 1] $.</span><span class="sxs-lookup"><span data-stu-id="8b1b9-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

