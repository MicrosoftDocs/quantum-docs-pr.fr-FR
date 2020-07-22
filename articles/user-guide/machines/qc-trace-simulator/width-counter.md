---
title: Compteur de largeur-Kit de développement Quantum
description: 'Découvrez le compteur Microsoft QDK Width, qui utilise le simulateur Quantum trace pour compter le nombre de qubits alloués et empruntés par des opérations dans un programme Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: af8609dc5c05f7a19b8d21755281427feb29b84c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871516"
---
# <a name="quantum-trace-simulator-width-counter"></a>Simulateur de traces Quantum : compteur de largeur

Le compteur de largeur fait partie du [simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)du kit de développement quantique. Vous pouvez l’utiliser pour compter le nombre d’qubits alloués et empruntés par chaque opération dans un programme Q #. Certaines opérations primitives peuvent allouer des qubits supplémentaires, par exemple, en multipliant des opérations contrôlées `X` ou des opérations contrôlées `T` .

## <a name="invoking-the-width-counter"></a>Appel du compteur de largeur

Pour exécuter le simulateur de traces de Quantum avec le compteur de largeur, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, affecter la `UseWidthCounter` **valeur true**à la propriété, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec le `QCTraceSimulatorConfiguration` comme paramètre. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Utilisation du compteur de largeur dans un programme hôte C#

L’exemple C# qui suit dans cette section calcule le nombre de qubits supplémentaires alloués par l’implémentation d’une opération contrôlée par multiplication <xref:microsoft.quantum.intrinsic.x> , en fonction de l’exemple de code Q # suivant :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

L’opération contrôlée <xref:microsoft.quantum.intrinsic.x> par multiplication agit sur un total de cinq qubits, alloue deux [qubits accessoires](xref:microsoft.quantum.glossary#ancilla)et a une largeur d’entrée de **5**. Utilisez le programme C# suivant pour vérifier les nombres :

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

La première partie du programme exécute l' `ApplyMultiControlledX` opération. La deuxième partie utilise la [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) méthode pour récupérer le nombre d’qubits alloués, ainsi que le nombre de qubits que l' `Controlled X` opération a reçu comme entrée. 

Enfin, vous pouvez générer toutes les statistiques collectées par le compteur de largeur au format CSV à l’aide des éléments suivants :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Voir aussi

- Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API.
