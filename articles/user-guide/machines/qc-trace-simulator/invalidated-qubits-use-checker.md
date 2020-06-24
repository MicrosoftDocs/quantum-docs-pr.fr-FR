---
title: Vérificateur d’utilisation de qubits non valide
description: 'En savoir plus sur l’outil de vérification de l’utilisation qubits Microsoft QDK invalidé, qui vérifie votre code Q # pour les qubits potentiellement non valides.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274903"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="62b66-103">Vérificateur d’utilisation de qubits non valide</span><span class="sxs-lookup"><span data-stu-id="62b66-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="62b66-104">Le `Invalidated Qubits Use Checker` fait partie de l’ordinateur Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) conçu pour détecter les bogues potentiels dans le code.</span><span class="sxs-lookup"><span data-stu-id="62b66-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="62b66-105">Examinez la partie suivante du code Q # pour illustrer les problèmes détectés par le `Invalidated Qubits Use Checker` .</span><span class="sxs-lookup"><span data-stu-id="62b66-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="62b66-106">Lorsque `H` est appliqué à `q[0]` , pointe vers un qubit déjà publié.</span><span class="sxs-lookup"><span data-stu-id="62b66-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="62b66-107">Cela peut entraîner un comportement indéfini.</span><span class="sxs-lookup"><span data-stu-id="62b66-107">This can cause undefined behavior.</span></span> <span data-ttu-id="62b66-108">Lorsque `Invalidated Qubits Use Checker` est activé, l’exception est `InvalidatedQubitsUseCheckerException` levée si une opération est appliquée à un qubit déjà publié.</span><span class="sxs-lookup"><span data-stu-id="62b66-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="62b66-109">Pour plus d’informations, consultez la documentation de l’API sur [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="62b66-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="62b66-110">Utilisation du vérificateur d’utilisation de qubits invalidé dans votre programme C#</span><span class="sxs-lookup"><span data-stu-id="62b66-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="62b66-111">Voici un exemple de code de pilote C# pour l’utilisation de l’ordinateur Quantum `Trace
Simulator` avec l' `Invalidated Qubits Use Checker` option Enabled :</span><span class="sxs-lookup"><span data-stu-id="62b66-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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

<span data-ttu-id="62b66-112">La classe `QCTraceSimulatorConfiguration` stocke la configuration du simulateur de trace d’ordinateur Quantum et peut être fournie en tant qu’argument pour le `QCTraceSimulator` constructeur.</span><span class="sxs-lookup"><span data-stu-id="62b66-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="62b66-113">Lorsque `useInvalidatedQubitsUseChecker` a la valeur true `Invalidated Qubits Use Checker` , le est activé.</span><span class="sxs-lookup"><span data-stu-id="62b66-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="62b66-114">Pour plus d’informations, consultez la documentation de l’API sur [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) et [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="62b66-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="62b66-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62b66-115">See also</span></span> ##

- <span data-ttu-id="62b66-116">Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="62b66-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
