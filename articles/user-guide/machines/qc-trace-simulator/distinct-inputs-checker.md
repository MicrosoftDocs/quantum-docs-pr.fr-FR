---
title: Vérificateur d’entrées distinctes-Kit de développement quantique
description: 'En savoir plus sur le vérificateur d’entrées distinct de Microsoft QDK, qui utilise le simulateur de traces Quantum pour vérifier votre code Q # en cas de conflit potentiel avec qubits partagé.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871142"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="58ee6-103">Simulateur de traces Quantum : vérificateur d’entrées distinct</span><span class="sxs-lookup"><span data-stu-id="58ee6-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="58ee6-104">L’outil de vérification des entrées distinct fait partie du [simulateur](xref:microsoft.quantum.machines.qc-trace-simulator.intro)Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="58ee6-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="58ee6-105">Vous pouvez l’utiliser pour détecter les bogues potentiels du code causés par des conflits avec des qubits partagés.</span><span class="sxs-lookup"><span data-stu-id="58ee6-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="58ee6-106">Conflits avec les qubits partagés</span><span class="sxs-lookup"><span data-stu-id="58ee6-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="58ee6-107">Examinez l’élément suivant du code Q # pour illustrer les problèmes détectés par l’outil de vérification des entrées distinct :</span><span class="sxs-lookup"><span data-stu-id="58ee6-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="58ee6-108">Lorsque vous examinez ce programme, vous pouvez supposer que l’ordre dans lequel il appelle `op1` et `op2` n’a pas d’importance, car `q1` et `q2` sont différents qubits et opérations agissant sur différents qubits.</span><span class="sxs-lookup"><span data-stu-id="58ee6-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="58ee6-109">À présent, prenons l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="58ee6-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="58ee6-110">Notez que `op1` et `op2` sont tous deux obtenus à l’aide de l’application partielle et partagent un qubit.</span><span class="sxs-lookup"><span data-stu-id="58ee6-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="58ee6-111">Lorsque vous appelez `ApplyBoth` dans cet exemple, le résultat de l’opération dépend de l’ordre de `op1` et de l’intérieur, pas de ce que `op2` `ApplyBoth` vous attendez.</span><span class="sxs-lookup"><span data-stu-id="58ee6-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="58ee6-112">Lorsque vous activez l’outil de vérification des entrées distinct, il détecte de telles situations et lève une `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="58ee6-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="58ee6-113">Pour plus d’informations, consultez <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> dans la bibliothèque d’API Q #.</span><span class="sxs-lookup"><span data-stu-id="58ee6-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="58ee6-114">Appel de l’outil d’analyse des entrées distinct</span><span class="sxs-lookup"><span data-stu-id="58ee6-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="58ee6-115">Pour exécuter le simulateur de traces de Quantum avec l’outil d’analyse des entrées distinct, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, définir la `UseDistinctInputsChecker` propriété sur **true**, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec `QCTraceSimulatorConfiguration` comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="58ee6-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="58ee6-116">Utilisation de l’outil de vérification des entrées distinct dans un programme hôte C#</span><span class="sxs-lookup"><span data-stu-id="58ee6-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="58ee6-117">Voici un exemple de programme hôte C# qui utilise le simulateur de traces Quantum avec l’outil de vérification des entrées distinct activé :</span><span class="sxs-lookup"><span data-stu-id="58ee6-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="58ee6-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58ee6-118">See also</span></span>

- <span data-ttu-id="58ee6-119">Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.</span><span class="sxs-lookup"><span data-stu-id="58ee6-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="58ee6-120">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="58ee6-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="58ee6-121">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="58ee6-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="58ee6-122">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API.</span><span class="sxs-lookup"><span data-stu-id="58ee6-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
