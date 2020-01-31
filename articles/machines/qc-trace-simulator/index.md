---
title: Simulateur de traces d’ordinateur quantique | Microsoft Docs
description: Vue d’ensemble du simulateur de traces d’ordinateur quantique
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 929745a6da6034599e97d2f573190308fde6eb75
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820434"
---
# <a name="quantum-trace-simulator"></a>Simulateur de traces quantiques

Le simulateur de traces quantiques de Microsoft exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique.  Pour cette raison, le simulateur de traces peut exécuter des programmes quantiques qui utilisent des milliers de qubits.  Il est utile à deux fins principales : 

* le débogage du code classique qui fait partie d’un programme quantique ; 
* l’estimation des ressources requises pour exécuter une instance donnée d’un programme quantique sur un ordinateur quantique.

Le simulateur de traces s’appuie sur des informations supplémentaires fournies par l’utilisateur lorsque des mesures doivent être effectuées. Pour plus d’informations à ce sujet, consultez la section [Génération de la probabilité des résultats de mesure](#providing-the-probability-of-measurement-outcomes). 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Génération de la probabilité des résultats de mesure

Il existe deux types de mesures qui apparaissent dans les algorithmes quantiques. Le premier type joue un rôle auxiliaire dans lequel l’utilisateur connaît généralement la probabilité des résultats. Dans ce cas, l’utilisateur peut écrire des <xref:microsoft.quantum.intrinsic.assertprob> à partir de l’espace de noms <xref:microsoft.quantum.intrinsic> pour exprimer cette connaissance. L'exemple suivant illustre ce mécanisme :

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Lorsque le simulateur de traces exécute `AssertProb`, il enregistre que la mesure de `PauliZ` sur `source` et `q` doit avoir un résultat de `Zero` avec une probabilité de 0,5. Lorsque le simulateur exécute `M` plus tard, il trouve les valeurs enregistrées des probabilités de résultat et `M` retourne `Zero` ou `One` avec une probabilité de 0,5. Quand le même code est exécuté sur un simulateur qui effectue le suivi de l’état quantique, ce simulateur vérifie que les probabilités fournies dans `AssertProb` sont correctes.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Exécution de votre programme avec le simulateur de traces d’ordinateur quantique 

Le simulateur de traces d’ordinateur quantique peut être considéré comme une autre machine cible. Le programme pilote en C# permettant de l’utiliser est très similaire à celui de tout autre simulateur quantique : 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Notez que s’il existe au moins une mesure qui n’est pas annotée à l’aide de `AssertProb`, le simulateur lèvera `UnconstrainedMeasurementException` à partir de l’espace de noms `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`. Pour plus d’informations, consultez la documentation de l’API sur [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException).

Outre l’exécution de programmes quantiques, le simulateur de traces dispose de cinq composants permettant la détection des bogues dans les programmes et l’exécution d’estimations de ressources pour les programmes quantiques : 

* [Vérificateur d’entrées distinctes](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Vérificateur d’utilisation de qubits non valides](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Compteur d’opérations primitives](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Compteur de profondeur du circuit](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Compteur de largeur du circuit](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Chacun de ces composants peut être activé en définissant les indicateurs appropriés dans `QCTraceSimulatorConfiguration`. Vous trouverez plus d’informations sur l’utilisation de chacun de ces composants dans les fichiers de référence correspondants. Pour plus d’informations, consultez la documentation de l’API sur [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="see-also"></a>Voir aussi
Référence en C# du [simulateur de traces](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) d’ordinateur quantique 

