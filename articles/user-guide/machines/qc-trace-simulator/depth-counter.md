---
title: Compteur de profondeur
description: Découvrez le compteur de profondeur Microsoft QDK, qui rassemble le nombre de la profondeur de chaque opération appelée dans un programme Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415258"
---
# <a name="depth-counter"></a>Compteur de profondeur

Le `Depth Counter` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace.
Il est utilisé pour rassembler des nombres qui représentent la limite inférieure de la profondeur de chaque opération appelée dans un programme Quantum. Toutes les opérations de <xref:microsoft.quantum.intrinsic> sont exprimées en termes de rotations à qubit unique, de grilles de T, de portes de qubit Clifford uniques, de portes cnotin et de mesures de plusieurs qubit Pauli observables. Les utilisateurs peuvent définir la profondeur de chacune des opérations primitives via le `gateTimes` champ de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

Par défaut, toutes les opérations ont la profondeur 0, à l’exception de la porte T qui a la profondeur 1. Cela signifie que, par défaut, seule la profondeur des opérations T est calculée (ce qui est souvent souhaitable). Les statistiques collectées sont agrégées sur tous les bords du graphique des appels d’opérations. 

Nous allons maintenant calculer la <xref:microsoft.quantum.intrinsic.t> profondeur de l' <xref:microsoft.quantum.intrinsic.ccnot> opération. Nous allons utiliser l’exemple de code Q # suivant :

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Utilisation du compteur Depth dans un programme C#

Pour vérifier que `CCNOT` a une `T` profondeur 5 et `ApplySampleWithCCNOT` a une `T` profondeur 6, nous pouvons utiliser le code C# suivant :

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

La première partie du programme s’exécute `ApplySampleWithCCNOT` . Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour connaître la `T` profondeur de `CCNOT` et `ApplySampleWithCCNOT` : 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Enfin, pour générer toutes les statistiques collectées au `Depth Counter` format CSV, nous pouvons utiliser les éléments suivants :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Voir aussi ##

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
