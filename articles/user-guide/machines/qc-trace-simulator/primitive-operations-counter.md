---
title: Compteur d’opérations primitifs
description: Découvrez le compteur d’opérations primitives de Microsoft QDK, qui effectue le suivi du nombre d’exécutions de primitives utilisées par les opérations dans un programme Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274893"
---
# <a name="primitive-operations-counter"></a>Compteur d’opérations primitifs  

Le `Primitive Operations Counter` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace. Il compte le nombre d’exécutions de primitives utilisées par chaque opération appelée dans un programme Quantum. Toutes les opérations de `Microsoft.Quantum.Intrinsic` sont exprimées en termes de rotations à qubit unique, de grilles de T, de portes de qubit Clifford uniques, de portes cnotin et de mesures de plusieurs qubit Pauli observables. Les statistiques collectées sont agrégées sur les bords du graphique des appels d’opérations. Nous allons maintenant compter le nombre `T` de portes nécessaires pour implémenter l' `CCNOT` opération. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Utilisation du compteur d’opérations primitifs dans un programme C#

Pour vérifier que `CCNOT` requiert 7 `T` portes et que `ApplySampleWithCCNOT` exécute 8 portes, `T` nous pouvons utiliser le code C# suivant :

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

La première partie du programme s’exécute `ApplySampleWithCCNOT` . Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour récupérer le nombre de portes T exécutées par `ApplySampleWithCCNOT` : 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Lorsque `GetMetric` est appelé avec deux paramètres de type, il retourne la valeur de la métrique associée à un bord de graphique d’appel donné. Dans notre exemple, `Primitive.CCNOT` l’opération est appelée dans `ApplySampleWithCCNOT` et par conséquent, le graphique des appels contient le bord `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Pour connaître le nombre de `CNOT` portes utilisées, nous pouvons ajouter la ligne suivante :
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Enfin, pour afficher toutes les statistiques collectées par le compteur de porte au format CSV, nous pouvons utiliser ce qui suit :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Voir aussi ##

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
