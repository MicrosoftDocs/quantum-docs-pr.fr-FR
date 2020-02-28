---
title: Vérificateur d’entrées distinct
description: 'En savoir plus sur le vérificateur d’entrées distinct de Microsoft QDK, qui vérifie votre code Q # pour identifier les conflits potentiels avec les qubits partagés.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907101"
---
# <a name="distinct-inputs-checker"></a>Vérificateur d’entrées distinct

Le `Distinct Inputs Checker` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace. Il est conçu pour détecter les bogues potentiels dans le code. Examinez l’élément suivant du code Q # pour illustrer les problèmes détectés par ce package :

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

Lorsque l’utilisateur regarde ce programme, il suppose que l’ordre dans lequel les `op1` et les `op2` sont appelés n’a pas d’importance, car `q1` et `q2` sont différents qubits et opérations agissant sur différents qubits. Prenons à présent un exemple, où cette opération est utilisée :

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

À présent `op1` et `op2` sont obtenus à l’aide d’une application partielle et partagent un qubit. Lorsque l’utilisateur appelle `ApplyBoth` dans l’exemple ci-dessus, le résultat de l’opération dépend de l’ordre de `op1` et `op2` dans `ApplyBoth`. C’est sans aucun doute ce que l’utilisateur s’attend à se produire. Le `Distinct Inputs Checker` détectera de telles situations lorsqu’il sera activé et lèvera `DistinctInputsCheckerException`. Pour plus d’informations, consultez la documentation de l’API sur [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Utilisation de l’outil d’analyse des C# entrées distinct dans votre programme

Voici un exemple de C# code de pilote permettant d’utiliser Quantum Computer trace Simulator avec l' `Distinct Inputs Checker` activée :

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

La classe `QCTraceSimulatorConfiguration` stocke la configuration du simulateur de trace d’ordinateur Quantum et peut être fournie en tant qu’argument pour le constructeur `QCTraceSimulator`. Lorsque `useDistinctInputsChecker` a la valeur true, la `Distinct Inputs Checker` est activée. Pour plus d’informations, consultez la documentation de l’API sur [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) et [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .

## <a name="see-also"></a>Voir aussi

- Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .
