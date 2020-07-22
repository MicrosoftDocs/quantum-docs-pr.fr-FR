---
title: Compteur d’opérations primitives-Kit de développement Quantum
description: 'Découvrez le compteur d’opérations primitives Microsoft QDK, qui utilise le simulateur de traces Quantum pour suivre les exécutions de primitives utilisées par les opérations dans un programme Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: ea022d499354f7cefd60da690466496e0ce7c336
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871023"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Simulateur de traces Quantum : compteur d’opérations primitives

Le compteur d’opérations primitifs fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Development Kit. Il compte le nombre d’exécutions de primitives utilisées par chaque opération appelée dans un programme Quantum. 

Toutes les <xref:microsoft.quantum.intrinsic> opérations sont exprimées en termes de rotations à qubit unique, d’opérations T, d’opérations de Clifford qubit, d’opérations cnotin et de mesures de plusieurs qubit Pauli observables. Le compteur opérations primitives agrège et collecte des statistiques sur tous les bords du [graphique des appels](https://en.wikipedia.org/wiki/Call_graph)de l’opération.

## <a name="invoking-the-primitive-operation-counter"></a>Appel du compteur d’opérations primitifs

Pour exécuter le simulateur de trace Quantum avec le compteur d’opérations primitifs, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, affecter la `UsePrimitiveOperationsCounter` **valeur true**à la propriété, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec le `QCTraceSimulatorConfiguration` comme paramètre.

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>Utilisation du compteur d’opérations primitifs dans un programme hôte C#

L’exemple C# qui suit dans cette section compte le nombre <xref:microsoft.quantum.intrinsic.t> d’opérations nécessaires pour implémenter l' <xref:microsoft.quantum.intrinsic.ccnot> opération, en fonction de l’exemple de code Q # suivant :

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Pour vérifier que `CCNOT` requiert sept `T` opérations et qu' `ApplySampleWithCCNOT` elle exécute huit `T` opérations, utilisez le code C# suivant :

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

La première partie du programme s’exécute `ApplySampleWithCCNOT` . La deuxième partie utilise la [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) méthode pour récupérer le nombre d' `T` opérations exécutées par `ApplySampleWithCCNOT` : 

Quand vous appelez `GetMetric` avec deux paramètres de type, elle retourne la valeur de la métrique associée à un bord de graphique d’appel donné. Dans l’exemple précédent, le programme appelle l' `Primitive.CCNOT` opération dans `ApplySampleWithCCNOT` et, par conséquent, le graphique des appels contient le bord `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Pour récupérer le nombre d' `CNOT` opérations utilisées, ajoutez la ligne suivante :
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Enfin, vous pouvez générer toutes les statistiques collectées par le compteur d’opérations primitives au format CSV à l’aide des éléments suivants :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Voir aussi

- Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API.