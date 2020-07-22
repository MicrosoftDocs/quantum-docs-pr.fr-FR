---
title: Vérificateur d’utilisation de qubits non valide-Kit de développement quantique
description: 'En savoir plus sur l’outil de vérification de l’utilisation qubits Microsoft QDK invalidé, qui utilise le simulateur de traces Quantum pour vérifier votre code Q # pour des qubits potentiellement non valides.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: fccf6d5784b587f4ad9b659e23027619acd06ffa
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871091"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="8e580-103">Simulateur de traces Quantum : vérificateur d’utilisation qubits invalidé</span><span class="sxs-lookup"><span data-stu-id="8e580-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="8e580-104">L’outil de vérification de l’utilisation de qubits invalidée fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="8e580-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="8e580-105">Vous pouvez l’utiliser pour détecter les bogues potentiels du code causés par des qubits non valides.</span><span class="sxs-lookup"><span data-stu-id="8e580-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="8e580-106">Qubits non valide</span><span class="sxs-lookup"><span data-stu-id="8e580-106">Invalid qubits</span></span>

<span data-ttu-id="8e580-107">Examinez l’élément suivant du code Q # pour illustrer les problèmes détectés par l’outil de vérification de l’utilisation des qubits invalidés :</span><span class="sxs-lookup"><span data-stu-id="8e580-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="8e580-108">Lorsque vous appliquez l' `H` opération à `q[0]` , elle pointe vers un qubit déjà publié, ce qui peut entraîner un comportement indéfini.</span><span class="sxs-lookup"><span data-stu-id="8e580-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="8e580-109">Lorsque l’outil de vérification de l’utilisation de qubits invalidée est activé, il lève l’exception `InvalidatedQubitsUseCheckerException` si le programme applique une opération à un qubit déjà publié.</span><span class="sxs-lookup"><span data-stu-id="8e580-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="8e580-110">Pour plus d’informations, consultez <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="8e580-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="8e580-111">Appel de l’outil de vérification de l’utilisation des qubits invalidés</span><span class="sxs-lookup"><span data-stu-id="8e580-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="8e580-112">Pour exécuter le simulateur de traces de Quantum avec le vérificateur d’utilisation qubits invalidé, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, définir la `UseInvalidatedQubitsUseChecker` propriété sur **true**, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec `QCTraceSimulatorConfiguration` comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="8e580-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="8e580-113">Utilisation de l’outil de vérification de l’utilisation des qubits invalidés dans un programme hôte C#</span><span class="sxs-lookup"><span data-stu-id="8e580-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="8e580-114">Voici un exemple de programmes hôtes C# qui utilisent le simulateur de traces Quantum avec l’option Invalid qubits use Checker activée :</span><span class="sxs-lookup"><span data-stu-id="8e580-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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

## <a name="see-also"></a><span data-ttu-id="8e580-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e580-115">See also</span></span>

- <span data-ttu-id="8e580-116">Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.</span><span class="sxs-lookup"><span data-stu-id="8e580-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="8e580-117">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="8e580-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="8e580-118">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="8e580-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="8e580-119">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API.</span><span class="sxs-lookup"><span data-stu-id="8e580-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>