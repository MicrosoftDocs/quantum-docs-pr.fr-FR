---
title: Simulateur de traces quantiques - Kit de développement Microsoft Quantum
description: Découvrez comment utiliser le simulateur de traces d’ordinateur quantiques de Microsoft pour déboguer du code classique et estimer les besoins en ressources d’un programme Q#.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5d5efef037ff236bd040dfd88e94f7f3dd331aef
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868217"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Simulateur de traces quantiques - Kit de développement Microsoft Quantum (QDK)

La classe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> du QDK exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique. Pour cette raison, le simulateur de traces quantiques peut exécuter des programmes quantiques qui utilisent des milliers de qubits.  Il est utile à deux fins principales : 

* le débogage du code classique qui fait partie d’un programme quantique ; 
* l’estimation des ressources requises pour exécuter une instance donnée d’un programme quantique sur un ordinateur quantique. En fait, l’[estimateur de ressources](xref:microsoft.quantum.machines.resources-estimator), qui fournit un ensemble de métriques plus limité, repose sur le simulateur de traces.

## <a name="invoking-the-quantum-trace-simulator"></a>Appel du simulateur de traces quantiques

Vous pouvez utiliser le simulateur de traces quantiques pour exécuter n’importe quelle opération Q#.

Comme pour les autres ordinateurs cibles, vous devez d’abord créer une instance de la classe `QCTraceSimulator`, puis la passer en tant que premier paramètre de la méthode `Run` d’une opération.

Notez que, contrairement à la classe `QuantumSimulator`, la classe `QCTraceSimulator` n’implémente pas l’interface <xref:System.IDisposable>. Vous n’avez donc pas besoin de la placer dans une instruction `using`.

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>Calcul de la probabilité des résultats de mesure

Étant donné que le simulateur de traces quantiques ne simule pas l’état quantique réel, il ne peut pas calculer la probabilité des résultats de mesure dans le cadre d’une opération. 

Par conséquent, si une opération comprend des mesures, vous devez fournir explicitement ces probabilités à l’aide de l’opération <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> à partir de l’espace de noms <xref:microsoft.quantum.diagnostics>. L'exemple suivant illustre ce mécanisme :

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Lorsque le simulateur de traces quantiques rencontre `AssertMeasurementProbability`, il enregistre que la mesure de `PauliZ` sur `source` et `q` doit avoir un résultat de `Zero` avec une probabilité de **0,5**. Lorsque plus tard, il exécutera l’opération `M`, il trouvera les valeurs enregistrées des probabilités de résultat. En outre, `M` retournera `Zero` ou `One`, avec une probabilité de **0,5**. Quand le même code est exécuté sur un simulateur qui effectue le suivi de l’état quantique, ce simulateur vérifie que les probabilités fournies dans `AssertMeasurementProbability` sont correctes.

Notez que s’il existe au moins une opération de mesure qui n’est pas annotée à l’aide de `AssertMeasurementProbability`, le simulateur lèvera une [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).

## <a name="quantum-trace-simulator-tools"></a>Outils du simulateur de traces quantiques

Le QDK comprend cinq outils que vous pouvez utiliser avec le simulateur de traces quantiques pour détecter les bogues de vos programmes et réaliser des estimations pour les ressources de votre programme quantique : 

|Outil | Description |
|-----| -----|
|[Vérificateur d’entrées distinctes](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |Recherche les conflits potentiels avec les qubits partagés |
|[Vérificateur d’utilisation de qubits non valides](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Vérifie si le programme applique une opération sur un qubit déjà publié |
|[Compteur d’opérations primitives](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Compte le nombre d’exécutions primitives utilisées par chaque opération appelée dans un programme quantique  |
|[Compteur de profondeur](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Rassemble les nombres qui représentent la limite inférieure de la profondeur de chaque opération appelée dans un programme quantique   |
|[Compteur de largeur](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Compte le nombre de qubits alloués et empruntés par chaque opération dans un programme quantique |

Chacun de ces outils est activé en définissant les indicateurs appropriés dans `QCTraceSimulatorConfiguration`, puis en passant la configuration à la déclaration `QCTraceSimulator`. Pour plus d’informations sur l’utilisation de chacun de ces outils, consultez les liens fournis dans la liste précédente. Pour plus d’informations sur la configuration de `QCTraceSimulator`, consultez [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>Méthodes QCTraceSimulator

`QCTraceSimulator` comprend plusieurs méthodes intégrées permettant de récupérer les valeurs des métriques suivies au cours d’une opération quantique. Vous trouverez des exemples pour les méthodes [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) et [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) dans les articles [Compteur d’opérations primitives](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Compteur de profondeur](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) et [Compteur de largeur](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter). Pour plus d’informations sur les méthodes disponibles, consultez [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) dans la référence de l’API Q#.  

## <a name="see-also"></a>Voir aussi

- [Estimateur de ressources quantiques](xref:microsoft.quantum.machines.resources-estimator)
- [Simulateur Toffoli quantique](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulateur d’état complet quantique](xref:microsoft.quantum.machines.full-state-simulator) 