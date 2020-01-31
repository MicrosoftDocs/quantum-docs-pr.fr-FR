---
title: Vérificateur d’utilisation de qubits invalidée | Simulateur de trace d’ordinateur Quantum | Microsoft Docs
description: Vue d’ensemble du simulateur de traces d’ordinateur quantique
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 093937346488725eacb69ef7da6affde764ec5c1
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820876"
---
# <a name="invalidated-qubits-use-checker"></a>Vérificateur d’utilisation de qubits non valide

Le `Invalidated Qubits Use Checker` fait partie de l’ordinateur Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) conçu pour détecter les bogues potentiels dans le code. Examinez l’élément suivant du code Q # pour illustrer les problèmes détectés par l' `Invalidated Qubits Use Checker`.

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Lorsque `H` est appliqué à `q[0]` il pointe vers un qubit déjà publié. Cela peut entraîner un comportement indéfini. Lorsque le `Invalidated Qubits Use Checker` est activé, l’exception `InvalidatedQubitsUseCheckerException` est levée si une opération est appliquée à un qubit déjà publié. Pour plus d’informations, consultez la documentation de l’API sur [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Utilisation du vérificateur d’utilisation de qubits invalidé dans votre C# programme

Voici un exemple de C# code de pilote pour l’utilisation de l’ordinateur Quantum `Trace
Simulator` avec l' `Invalidated Qubits Use Checker` activée : 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

La classe `QCTraceSimulatorConfiguration` stocke la configuration du simulateur de trace d’ordinateur Quantum et peut être fournie en tant qu’argument pour le constructeur `QCTraceSimulator`. Lorsque `useInvalidatedQubitsUseChecker` a la valeur true, la `Invalidated Qubits Use Checker` est activée. Pour plus d’informations, consultez la documentation de l’API sur [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) et [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .

## <a name="see-also"></a>Voir aussi ##

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
