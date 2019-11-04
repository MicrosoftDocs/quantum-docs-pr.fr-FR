---
title: Compteur d’opérations primitifs | Simulateur de trace d’ordinateur Quantum | Microsoft Docs
description: Vue d’ensemble du simulateur de trace d’ordinateur Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184880"
---
# <a name="primitive-operations-counter"></a>Compteur d’opérations primitifs  

Le `Primitive Operations Counter` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace. Il compte le nombre d’exécutions de primitives utilisées par chaque opération appelée dans un programme Quantum. Toutes les opérations à partir de `Microsoft.Quantum.Primitive` sont exprimées en termes de rotations qubit uniques, de grilles de qubit Clifford uniques, de portes CNOTIN et de mesures de qubit Pauli observables. Les statistiques collectées sont agrégées sur les bords du graphique des appels d’opérations. Nous allons maintenant compter le nombre de `T` de portes nécessaires pour implémenter l’opération de `CCNOT`. 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Utilisation du compteur d’opérations primitifs C# dans un programme

Pour vérifier que `CCNOT` a effectivement besoin de 7 `T` portes et que `CCNOTDriver` exécute 8 `T` portes, nous pouvons utiliser C# le code suivant :

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

La première partie du programme exécute `CCNOTDriver`. Dans la deuxième partie, nous utilisons la méthode `QCTraceSimulator.GetMetric` pour récupérer le nombre de portes T exécutées par `CCNOTDriver`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

Lorsque `GetMetric` est appelée avec deux paramètres de type, il retourne la valeur de la métrique associée à un bord de graphique d’appel donné. Dans notre exemple d’opération `Primitive.CCNOT` est appelé dans `CCNOTDriver` et, par conséquent, le graphique des appels contient le `<Primitive.CCNOT,CCNOTDriver>`Edge. 

Pour connaître le nombre de `CNOT` portes utilisées, nous pouvons ajouter la ligne suivante :
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

Enfin, pour afficher toutes les statistiques collectées par le compteur de porte au format CSV, nous pouvons utiliser ce qui suit :
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Consultez également la section ##

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
