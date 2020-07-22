---
title: Compteur de profondeur-Kit de développement quantique
description: 'En savoir plus sur le compteur de profondeur de Microsoft QDK, qui utilise le simulateur de traces Quantum pour collecter le nombre de niveaux de la profondeur de chaque opération appelée dans un programme Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 811e387fedf547d2681518ae0bb525c13dc84ff4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871125"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Simulateur de traces Quantum : compteur de profondeur

Le compteur de profondeur fait partie du [simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)du kit de développement quantique.
Vous pouvez l’utiliser pour rassembler des nombres qui représentent la limite inférieure de la profondeur de chaque opération appelée dans un programme Quantum. 

## <a name="depth-values"></a>Valeurs de profondeur

Par défaut, toutes les opérations ont une profondeur égale à **0** , à l’exception de l' `T` opération, dont la profondeur est égale à **1**. Cela signifie que, par défaut, seule la `T` profondeur des opérations est calculée (ce qui est souvent souhaitable). Le compteur de profondeur agrège et collecte des statistiques sur tous les bords du [graphique des appels](https://en.wikipedia.org/wiki/Call_graph)de l’opération.

Toutes les <xref:microsoft.quantum.intrinsic> opérations sont exprimées en termes de rotations à qubit unique, d' <xref:microsoft.quantum.intrinsic.t> opérations, d’opérations de Clifford à qubit unique, <xref:microsoft.quantum.intrinsic.cnot> d’opérations et de mesures de plusieurs qubit Pauli observables. Les utilisateurs peuvent définir la profondeur de chacune des opérations primitives via le `gateTimes` champ de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>Appel du compteur de profondeur

Pour exécuter le simulateur de trace Quantum avec le compteur Depth, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, affecter la `UseDepthCounter` **valeur true**à sa propriété, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec `QCTraceSimulatorConfiguration` comme paramètre. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>Utilisation du compteur Depth dans un programme hôte C#

L’exemple C# qui suit dans cette section calcule la `T` profondeur de l' `CCNOT` opération, en fonction de l’exemple de code Q # suivant :

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Pour vérifier que `CCNOT` a `T` la profondeur **5** et `ApplySampleWithCCNOT` a une `T` profondeur **6**, utilisez le code C# suivant :

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

La première partie du programme s’exécute `ApplySampleWithCCNOT` . La deuxième partie utilise la [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) méthode pour récupérer la `T` profondeur de `CCNOT` et `ApplySampleWithCCNOT` . 

Enfin, vous pouvez générer toutes les statistiques collectées par le compteur de profondeur au format CSV à l’aide des éléments suivants :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Voir aussi

- Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API.
