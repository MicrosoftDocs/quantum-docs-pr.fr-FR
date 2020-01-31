---
title: Compteur de largeur | Simulateur de trace d’ordinateur Quantum | Microsoft Docs
description: Vue d’ensemble du simulateur de traces d’ordinateur quantique
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820366"
---
# <a name="width-counter"></a>Compteur de largeur

Le `Width Counter` compte le nombre d’qubits alloués et empruntés par chaque opération.
Toutes les opérations de l’espace de noms `Microsoft.Quantum.Intrinsic` sont exprimées en termes de rotations qubit simples, de portes T, de portes qubit Clifford simples, de portes CNOTIN et de mesures de plusieurs qubit Pauli observables. Certaines opérations primitives peuvent allouer des qubits supplémentaires. Par exemple, multiplier les portes `X` contrôlées ou contrôler les portes `T`. Nous allons calculer le nombre de qubits supplémentaires alloués par l’implémentation d’une porte de `X` contrôlée par multiplication :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Utilisation d’un compteur de C# largeur dans un programme

La multiplication des `X` contrôlées agissant sur un total de 5 qubits allouera 2 qubits accessoires et sa largeur d’entrée sera de 5. Pour vérifier que c’est le cas, nous pouvons utiliser le programme C# suivant :

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

La première partie du programme exécute `ApplyMultiControlledX`. Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour connaître le nombre de qubits alloués, ainsi que le nombre de qubits qui ont contrôlé `X` reçu en entrée. 

Enfin, pour générer toutes les statistiques collectées par le compteur de largeur au format CSV, nous pouvons utiliser ce qui suit :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Voir aussi ##

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
