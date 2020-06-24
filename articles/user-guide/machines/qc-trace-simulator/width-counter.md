---
title: Compteur de largeur
description: Découvrez le compteur Microsoft QDK Width, qui compte le nombre de qubits alloués et empruntés par chaque opération dans un programme Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274894"
---
# <a name="width-counter"></a>Compteur de largeur

Le `Width Counter` compte le nombre d’qubits alloués et empruntés par chaque opération.
Toutes les opérations de l' `Microsoft.Quantum.Intrinsic` espace de noms sont exprimées en termes de rotations qubit uniques, de portes T, de portes qubit Clifford simples, de portes cnotin et de mesures de plusieurs qubit Pauli observables. Certaines opérations primitives peuvent allouer des qubits supplémentaires. Par exemple, multiplier les `X` portes contrôlées ou les portes contrôlées `T` . Nous allons calculer le nombre de qubits supplémentaires alloués par l’implémentation d’une porte gérée par multiplication `X` :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Utilisation d’un compteur de largeur dans un programme C#

La multiplication contrôlée `X` agissant sur un total de 5 qubits allouera 2 qubits accessoires et sa largeur d’entrée sera de 5. Pour vérifier que c’est le cas, nous pouvons utiliser le programme C# suivant :

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

La première partie du programme s’exécute `ApplyMultiControlledX` . Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour connaître le nombre d’qubits alloués, ainsi que le nombre de qubits qui `X` ont été contrôlés comme entrée. 

Enfin, pour générer toutes les statistiques collectées par le compteur de largeur au format CSV, nous pouvons utiliser ce qui suit :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Voir aussi ##

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
