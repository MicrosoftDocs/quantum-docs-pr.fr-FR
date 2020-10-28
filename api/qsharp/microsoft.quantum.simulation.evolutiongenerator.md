---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: Type défini par l’utilisateur EvolutionGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: be741216bf99305bf5f1d149c815e98aba36aad1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701752"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="dc20e-102">Type défini par l’utilisateur EvolutionGenerator</span><span class="sxs-lookup"><span data-stu-id="dc20e-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="dc20e-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dc20e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dc20e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc20e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc20e-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion en termes de cette base.</span><span class="sxs-lookup"><span data-stu-id="dc20e-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="dc20e-106">Dernier paramètre pour le nombre de termes.</span><span class="sxs-lookup"><span data-stu-id="dc20e-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

