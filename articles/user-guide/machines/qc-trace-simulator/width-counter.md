---
title: Compteur de largeur-Kit de développement Quantum
description: 'Découvrez le compteur Microsoft QDK Width, qui utilise le simulateur Quantum trace pour compter le nombre de qubits alloués et empruntés par des opérations dans un programme Q #.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: af8609dc5c05f7a19b8d21755281427feb29b84c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871516"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="a7491-103">Simulateur de traces Quantum : compteur de largeur</span><span class="sxs-lookup"><span data-stu-id="a7491-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="a7491-104">Le compteur de largeur fait partie du [simulateur de traces Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)du kit de développement quantique.</span><span class="sxs-lookup"><span data-stu-id="a7491-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="a7491-105">Vous pouvez l’utiliser pour compter le nombre d’qubits alloués et empruntés par chaque opération dans un programme Q #.</span><span class="sxs-lookup"><span data-stu-id="a7491-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="a7491-106">Certaines opérations primitives peuvent allouer des qubits supplémentaires, par exemple, en multipliant des opérations contrôlées `X` ou des opérations contrôlées `T` .</span><span class="sxs-lookup"><span data-stu-id="a7491-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="a7491-107">Appel du compteur de largeur</span><span class="sxs-lookup"><span data-stu-id="a7491-107">Invoking the width counter</span></span>

<span data-ttu-id="a7491-108">Pour exécuter le simulateur de traces de Quantum avec le compteur de largeur, vous devez créer une <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, affecter la `UseWidthCounter` **valeur true**à la propriété, puis créer une nouvelle <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance avec le `QCTraceSimulatorConfiguration` comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="a7491-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="a7491-109">Utilisation du compteur de largeur dans un programme hôte C#</span><span class="sxs-lookup"><span data-stu-id="a7491-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="a7491-110">L’exemple C# qui suit dans cette section calcule le nombre de qubits supplémentaires alloués par l’implémentation d’une opération contrôlée par multiplication <xref:microsoft.quantum.intrinsic.x> , en fonction de l’exemple de code Q # suivant :</span><span class="sxs-lookup"><span data-stu-id="a7491-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="a7491-111">L’opération contrôlée <xref:microsoft.quantum.intrinsic.x> par multiplication agit sur un total de cinq qubits, alloue deux [qubits accessoires](xref:microsoft.quantum.glossary#ancilla)et a une largeur d’entrée de **5**.</span><span class="sxs-lookup"><span data-stu-id="a7491-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="a7491-112">Utilisez le programme C# suivant pour vérifier les nombres :</span><span class="sxs-lookup"><span data-stu-id="a7491-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="a7491-113">La première partie du programme exécute l' `ApplyMultiControlledX` opération.</span><span class="sxs-lookup"><span data-stu-id="a7491-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="a7491-114">La deuxième partie utilise la [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) méthode pour récupérer le nombre d’qubits alloués, ainsi que le nombre de qubits que l' `Controlled X` opération a reçu comme entrée.</span><span class="sxs-lookup"><span data-stu-id="a7491-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="a7491-115">Enfin, vous pouvez générer toutes les statistiques collectées par le compteur de largeur au format CSV à l’aide des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a7491-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="a7491-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7491-116">See also</span></span>

- <span data-ttu-id="a7491-117">Vue d’ensemble du [simulateur Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Development Kit.</span><span class="sxs-lookup"><span data-stu-id="a7491-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="a7491-118">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="a7491-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="a7491-119">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="a7491-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="a7491-120">Référence de l' <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API.</span><span class="sxs-lookup"><span data-stu-id="a7491-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
