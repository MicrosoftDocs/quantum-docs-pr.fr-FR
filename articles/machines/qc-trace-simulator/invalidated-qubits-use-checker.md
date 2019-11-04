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
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="96268-103">Vérificateur d’utilisation de qubits non valide</span><span class="sxs-lookup"><span data-stu-id="96268-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="96268-104">Le `Invalidated Qubits Use Checker` fait partie de l’ordinateur Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) conçu pour détecter les bogues potentiels dans le code.</span><span class="sxs-lookup"><span data-stu-id="96268-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="96268-105">Examinez l’élément suivant du code Q # pour illustrer les problèmes détectés par l' `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="96268-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubitTest () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="96268-106">Lorsque `H` est appliqué à `q[0]` il pointe vers un qubit déjà publié.</span><span class="sxs-lookup"><span data-stu-id="96268-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="96268-107">Cela peut entraîner un comportement indéfini.</span><span class="sxs-lookup"><span data-stu-id="96268-107">This can cause undefined behavior.</span></span> <span data-ttu-id="96268-108">Lorsque le `Invalidated Qubits Use Checker` est activé, l’exception `InvalidatedQubitsUseCheckerException` est levée si une opération est appliquée à un qubit déjà publié.</span><span class="sxs-lookup"><span data-stu-id="96268-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="96268-109">Pour plus d’informations, consultez la documentation de l’API sur [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) .</span><span class="sxs-lookup"><span data-stu-id="96268-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="96268-110">Utilisation du vérificateur d’utilisation de qubits invalidé dans votre C# programme</span><span class="sxs-lookup"><span data-stu-id="96268-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="96268-111">Voici un exemple de C# code de pilote pour l’utilisation de l’ordinateur Quantum `Trace
Simulator` avec l' `Invalidated Qubits Use Checker` activée :</span><span class="sxs-lookup"><span data-stu-id="96268-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="96268-112">La classe `QCTraceSimulatorConfiguration` stocke la configuration du simulateur de trace d’ordinateur Quantum et peut être fournie en tant qu’argument pour le constructeur `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="96268-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="96268-113">Lorsque `useInvalidatedQubitsUseChecker` a la valeur true, la `Invalidated Qubits Use Checker` est activée.</span><span class="sxs-lookup"><span data-stu-id="96268-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="96268-114">Pour plus d’informations, consultez la documentation de l’API sur [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) et [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="96268-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="96268-115">Consultez également la section</span><span class="sxs-lookup"><span data-stu-id="96268-115">See also</span></span> ##

- <span data-ttu-id="96268-116">Présentation de Quantum Computer [trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) .</span><span class="sxs-lookup"><span data-stu-id="96268-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
