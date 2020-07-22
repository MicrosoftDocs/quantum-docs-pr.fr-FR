---
title: Simulateur Quantum à état complet-Kit de développement quantique
description: 'Découvrez comment exécuter vos programmes Q # sur le simulateur d’état Microsoft Quantum Development Kit.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871176"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="df604-103">Simulateur d’état complet du kit de développement quantique (QDK)</span><span class="sxs-lookup"><span data-stu-id="df604-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="df604-104">QDK fournit un simulateur d’état complet qui simule un ordinateur quantique sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="df604-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="df604-105">Vous pouvez utiliser le simulateur d’état complet pour exécuter et déboguer des algorithmes Quantum écrits en Q #, en utilisant jusqu’à 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="df604-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="df604-106">Le simulateur d’état complet est semblable au simulateur Quantum utilisé dans la plateforme [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="df604-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="df604-107">Appel et exécution du simulateur d’état complet</span><span class="sxs-lookup"><span data-stu-id="df604-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="df604-108">Vous exposez le simulateur d’état complet par le biais de la `QuantumSimulator` classe.</span><span class="sxs-lookup"><span data-stu-id="df604-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="df604-109">Pour plus d’informations, consultez [méthodes d’exécution d’un programme Q #](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="df604-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="df604-110">Appel du simulateur à partir de C #</span><span class="sxs-lookup"><span data-stu-id="df604-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="df604-111">Créez une instance de la `QuantumSimulator` classe, puis transmettez-la à la `Run` méthode d’une opération de Quantum, ainsi que tous les paramètres supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="df604-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="df604-112">Étant donné que la `QuantumSimulator` classe implémente l' <xref:System.IDisposable> interface, vous devez appeler la `Dispose` méthode une fois que vous n’avez plus besoin de l’instance du simulateur.</span><span class="sxs-lookup"><span data-stu-id="df604-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="df604-113">La meilleure façon de procéder consiste à encapsuler la déclaration et les opérations du simulateur dans une instruction [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , qui appelle automatiquement la `Dispose` méthode.</span><span class="sxs-lookup"><span data-stu-id="df604-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="df604-114">Appel du simulateur à partir de Python</span><span class="sxs-lookup"><span data-stu-id="df604-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="df604-115">Utilisez la méthode [simulation ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) de la bibliothèque t # Python avec l’opération q # importée :</span><span class="sxs-lookup"><span data-stu-id="df604-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="df604-116">Appel du simulateur à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="df604-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="df604-117">Lors de l’exécution d’un programme Q # à partir de la ligne de commande, le simulateur d’état complet est l’ordinateur cible par défaut.</span><span class="sxs-lookup"><span data-stu-id="df604-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="df604-118">Si vous le souhaitez, vous pouvez utiliser le paramètre **--simulateur** (ou **-s** shortcut) pour spécifier l’ordinateur cible souhaité.</span><span class="sxs-lookup"><span data-stu-id="df604-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="df604-119">Les deux commandes suivantes exécutent un programme à l’aide du simulateur d’état complet.</span><span class="sxs-lookup"><span data-stu-id="df604-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="df604-120">Appel du simulateur à partir d’un bloc-notes Juptyer</span><span class="sxs-lookup"><span data-stu-id="df604-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="df604-121">Utilisez la commande IQ # Magic [% simulation](xref:microsoft.quantum.iqsharp.magic-ref.simulate) pour exécuter l’opération Q #.</span><span class="sxs-lookup"><span data-stu-id="df604-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="df604-122">Amorçage du simulateur</span><span class="sxs-lookup"><span data-stu-id="df604-122">Seeding the simulator</span></span>

<span data-ttu-id="df604-123">Par défaut, le simulateur d’état complet utilise un générateur de nombres aléatoires pour simuler le caractère aléatoire du quantum.</span><span class="sxs-lookup"><span data-stu-id="df604-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="df604-124">À des fins de test, il est parfois utile d’avoir des résultats déterministes.</span><span class="sxs-lookup"><span data-stu-id="df604-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="df604-125">Dans un programme C#, vous pouvez le faire en fournissant une valeur de départ pour le générateur de nombres aléatoires dans le `QuantumSimulator` constructeur via le `randomNumberGeneratorSeed` paramètre.</span><span class="sxs-lookup"><span data-stu-id="df604-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="df604-126">Configuration des threads</span><span class="sxs-lookup"><span data-stu-id="df604-126">Configuring threads</span></span>

<span data-ttu-id="df604-127">Le simulateur d’état complet utilise [OpenMP](http://www.openmp.org/) pour paralléliser l’algèbre linéaire requis.</span><span class="sxs-lookup"><span data-stu-id="df604-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="df604-128">Par défaut, OpenMP utilise tous les threads matériels disponibles, ce qui signifie que les programmes avec un petit nombre de qubits s’exécutent souvent lentement, car la coordination requise expose le travail réel.</span><span class="sxs-lookup"><span data-stu-id="df604-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="df604-129">Vous pouvez résoudre ce problème en définissant la variable `OMP_NUM_THREADS` d’environnement sur un petit nombre.</span><span class="sxs-lookup"><span data-stu-id="df604-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="df604-130">En règle générale, configurez un thread pour un maximum de quatre qubits, puis un thread supplémentaire par qubit.</span><span class="sxs-lookup"><span data-stu-id="df604-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="df604-131">Vous devrez peut-être ajuster la variable en fonction de votre algorithme.</span><span class="sxs-lookup"><span data-stu-id="df604-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="df604-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df604-132">See also</span></span>

- [<span data-ttu-id="df604-133">Estimateur de ressources de Quantum</span><span class="sxs-lookup"><span data-stu-id="df604-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="df604-134">Simulateur Quantum Toffoli</span><span class="sxs-lookup"><span data-stu-id="df604-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="df604-135">Simulateur de traces Quantum</span><span class="sxs-lookup"><span data-stu-id="df604-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)