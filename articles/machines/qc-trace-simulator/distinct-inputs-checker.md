---
title: Vérificateur d’entrées distinct | Simulateur de trace d’ordinateur Quantum | Microsoft Docs
description: Vue d’ensemble du simulateur de traces d’ordinateur quantique
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 3c21a54f5da83bf1ea0792e79cc773be5fba71e8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820961"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="54eab-103">Vérificateur d’entrées distinct</span><span class="sxs-lookup"><span data-stu-id="54eab-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="54eab-104">Le `Distinct Inputs Checker` fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Computer trace.</span><span class="sxs-lookup"><span data-stu-id="54eab-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="54eab-105">Il est conçu pour détecter les bogues potentiels dans le code.</span><span class="sxs-lookup"><span data-stu-id="54eab-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="54eab-106">Examinez l’élément suivant du code Q # pour illustrer les problèmes détectés par ce package :</span><span class="sxs-lookup"><span data-stu-id="54eab-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="54eab-107">Lorsque l’utilisateur regarde ce programme, il suppose que l’ordre dans lequel les `op1` et les `op2` sont appelés n’a pas d’importance, car `q1` et `q2` sont différents qubits et opérations agissant sur différents qubits.</span><span class="sxs-lookup"><span data-stu-id="54eab-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="54eab-108">Prenons à présent un exemple, où cette opération est utilisée :</span><span class="sxs-lookup"><span data-stu-id="54eab-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="54eab-109">À présent `op1` et `op2` sont obtenus à l’aide d’une application partielle et partagent un qubit.</span><span class="sxs-lookup"><span data-stu-id="54eab-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="54eab-110">Lorsque l’utilisateur appelle `ApplyBoth` dans l’exemple ci-dessus, le résultat de l’opération dépend de l’ordre de `op1` et `op2` dans `ApplyBoth`.</span><span class="sxs-lookup"><span data-stu-id="54eab-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="54eab-111">C’est sans aucun doute ce que l’utilisateur s’attend à se produire.</span><span class="sxs-lookup"><span data-stu-id="54eab-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="54eab-112">Le `Distinct Inputs Checker` détectera de telles situations lorsqu’il sera activé et lèvera `DistinctInputsCheckerException`.</span><span class="sxs-lookup"><span data-stu-id="54eab-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="54eab-113">Pour plus d’informations, consultez la documentation de l’API sur [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="54eab-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="54eab-114">Utilisation de l’outil d’analyse des C# entrées distinct dans votre programme</span><span class="sxs-lookup"><span data-stu-id="54eab-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="54eab-115">Voici un exemple de C# code de pilote permettant d’utiliser Quantum Computer trace Simulator avec l' `Distinct Inputs Checker` activée :</span><span class="sxs-lookup"><span data-stu-id="54eab-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="54eab-116">La classe `QCTraceSimulatorConfiguration` stocke la configuration du simulateur de trace d’ordinateur Quantum et peut être fournie en tant qu’argument pour le constructeur `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="54eab-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="54eab-117">Lorsque `useDistinctInputsChecker` a la valeur true, la `Distinct Inputs Checker` est activée.</span><span class="sxs-lookup"><span data-stu-id="54eab-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="54eab-118">Pour plus d’informations, consultez la documentation de l’API sur [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) et [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) .</span><span class="sxs-lookup"><span data-stu-id="54eab-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="54eab-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54eab-119">See also</span></span>

- <span data-ttu-id="54eab-120">Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="54eab-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
