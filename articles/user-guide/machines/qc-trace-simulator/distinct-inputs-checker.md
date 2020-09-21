---
title: Vérificateur d’entrées distinctes-Kit de développement quantique
description: En savoir plus sur l’outil de vérification des entrées distinct de Microsoft QDK, qui utilise le simulateur de traces Quantum pour vérifier si votre Q# code présente des conflits potentiels avec les qubits partagés.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: bcb0bc92a546279496d27ad9b8c5f943ac133e2a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833467"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Simulateur de traces Quantum : vérificateur d’entrées distinct

L’outil de vérification des entrées distinct fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Development Kit. Vous pouvez l’utiliser pour détecter les bogues potentiels du code causés par des conflits avec des qubits partagés. 

## <a name="conflicts-with-shared-qubits"></a>Conflits avec les qubits partagés

Considérez le morceau de Q# code suivant pour illustrer les problèmes détectés par l’outil de vérification des entrées distinct :

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

Lorsque vous examinez ce programme, vous pouvez supposer que l’ordre dans lequel il appelle `op1` et `op2` n’a pas d’importance, car `q1` et `q2` sont différents qubits et opérations agissant sur différents qubits. 

À présent, prenons l’exemple suivant :

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Notez que `op1` et `op2` sont tous deux obtenus à l’aide de l’application partielle et partagent un qubit. Lorsque vous appelez `ApplyBoth` dans cet exemple, le résultat de l’opération dépend de l’ordre de `op1` et de l’intérieur, pas de ce que `op2` `ApplyBoth` vous attendez. Lorsque vous activez l’outil de vérification des entrées distinct, il détecte de telles situations et lève une `DistinctInputsCheckerException` . Pour plus d’informations, consultez <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> dans la Q# bibliothèque d’API.

## <a name="invoking-the-distinct-inputs-checker"></a>Appel de l’outil d’analyse des entrées distinct

Pour exécuter le simulateur de traces de Quantum avec l’outil d’analyse des entrées distinct, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, définir la `UseDistinctInputsChecker` propriété sur **true**, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec `QCTraceSimulatorConfiguration` comme paramètre. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>Utilisation de l’outil de vérification des entrées distinct dans un programme hôte C#

Voici un exemple de programme hôte C# qui utilise le simulateur de traces Quantum avec l’outil de vérification des entrées distinct activé :

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
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
- Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API.
