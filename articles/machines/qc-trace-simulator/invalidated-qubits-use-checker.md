---
title: Vérificateur d’utilisation de qubits invalidée | Simulateur de trace d’ordinateur Quantum | Microsoft Docs
description: Vue d’ensemble du simulateur de trace d’ordinateur Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 7403381b995ab660aa5cbc5a52b1e12c5c9ce442
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184965"
---
# <a name="invalidated-qubits-use-checker"></a>Vérificateur d’utilisation de qubits non valide

Le `Invalidated Qubits Use Checker` fait partie de l’ordinateur Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) conçu pour détecter les bogues potentiels dans le code. Examinez l’élément suivant du code Q # pour illustrer les problèmes détectés par l' `Invalidated Qubits Use Checker`.

```qsharp
operation UseReleasedQubitTest () : Unit {
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

## <a name="see-also"></a>Consultez également la section ##

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
