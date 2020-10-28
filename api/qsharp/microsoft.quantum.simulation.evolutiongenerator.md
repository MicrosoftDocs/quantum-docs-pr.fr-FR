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
# <a name="evolutiongenerator-user-defined-type"></a>Type défini par l’utilisateur EvolutionGenerator

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion en termes de cette base.

Dernier paramètre pour le nombre de termes.

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

