---
title: Vérificateur d’utilisation de qubits non valide-Kit de développement quantique
description: En savoir plus sur l’outil de vérification de l’utilisation du qubits Microsoft QDK invalidé, qui utilise le simulateur de traces Quantum pour vérifier si votre Q# code comporte des qubits potentiellement non valides.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 18371b3798d0eaa12d4e7107f58f44379594619f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835993"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Simulateur de traces Quantum : vérificateur d’utilisation qubits invalidé

L’outil de vérification de l’utilisation de qubits invalidée fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Development Kit. Vous pouvez l’utiliser pour détecter les bogues potentiels du code causés par des qubits non valides. 

## <a name="invalid-qubits"></a>Qubits non valide

Considérez le morceau de Q# code suivant pour illustrer les problèmes détectés par l’outil Invalid qubits use Checker :

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Lorsque vous appliquez l' `H` opération à `q[0]` , elle pointe vers un qubit déjà publié, ce qui peut entraîner un comportement indéfini. Lorsque l’outil de vérification de l’utilisation de qubits invalidée est activé, il lève l’exception `InvalidatedQubitsUseCheckerException` si le programme applique une opération à un qubit déjà publié. Pour plus d'informations, consultez <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>Appel de l’outil de vérification de l’utilisation des qubits invalidés

Pour exécuter le simulateur de traces de Quantum avec le vérificateur d’utilisation qubits invalidé, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, définir la `UseInvalidatedQubitsUseChecker` propriété sur **true**, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec `QCTraceSimulatorConfiguration` comme paramètre. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>Utilisation de l’outil de vérification de l’utilisation des qubits invalidés dans un programme hôte C#

Voici un exemple de programmes hôtes C# qui utilisent le simulateur de traces Quantum avec l’option Invalid qubits use Checker activée : 

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>Voir aussi

- Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API.