---
title: Compteur de profondeur
description: Découvrez le compteur de profondeur Microsoft QDK, qui rassemble le nombre de la profondeur de chaque opération appelée dans un programme Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906098"
---
# <a name="depth-counter"></a>Compteur de profondeur

Le `Depth Counter` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace.
Il est utilisé pour regrouper les nombres de la profondeur de chaque opération appelée dans un programme Quantum. Toutes les opérations à partir de <xref:microsoft.quantum.intrinsic> sont exprimées en termes de rotations qubit uniques, de grilles de qubit Clifford uniques, de portes CNOTIN et de mesures de qubit Pauli observables. Les utilisateurs peuvent définir la profondeur de chacune des opérations primitives via le champ `gateTimes` de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.

Par défaut, toutes les opérations ont la profondeur 0, à l’exception de la porte T qui a la profondeur 1. Cela signifie que, par défaut, seule la profondeur des opérations T est calculée (ce qui est souvent souhaitable). Les statistiques collectées sont agrégées sur tous les bords du graphique des appels d’opérations. 

Calculons à présent le <xref:microsoft.quantum.intrinsic.t> profondeur de l’opération <xref:microsoft.quantum.intrinsic.ccnot>. Nous allons utiliser l’exemple de code Q # suivant :

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Utilisation du compteur de profondeur C# dans un programme

Pour vérifier que `CCNOT` a `T` profondeur 5 et que `ApplySampleWithCCNOT` a `T` profondeur 6, nous pouvons utiliser C# le code suivant :

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

La première partie du programme exécute `ApplySampleWithCCNOT`. Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour connaître l' `T` profondeur de `CCNOT` et `ApplySampleWithCCNOT`: 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Enfin, pour générer toutes les statistiques collectées par `Depth Counter` au format CSV, nous pouvons utiliser les éléments suivants :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Voir aussi ##

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
