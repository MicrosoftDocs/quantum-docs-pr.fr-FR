---
title: Simulateur d’état complet
description: 'Découvrez comment exécuter vos programmes Q # sur le simulateur d’état Microsoft Quantum Development Kit.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274944"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="cfa8e-103">Simulateur d’état complet du kit de développement quantique</span><span class="sxs-lookup"><span data-stu-id="cfa8e-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="cfa8e-104">Le kit de développement quantum fournit un simulateur Quantum d’état complet similaire à [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="cfa8e-105">Ce simulateur peut être utilisé pour exécuter et déboguer des algorithmes de Quantum écrits en Q # sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="cfa8e-106">Ce simulateur Quantum est exposé via la `QuantumSimulator` classe.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="cfa8e-107">Pour utiliser le simulateur, il vous suffit de créer une instance de cette classe et de la passer à la `Run` méthode de l’opération Quantum que vous souhaitez exécuter avec le reste des paramètres :</span><span class="sxs-lookup"><span data-stu-id="cfa8e-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="cfa8e-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="cfa8e-108">IDisposable</span></span>

<span data-ttu-id="cfa8e-109">La `QuantumSimulator` classe implémente <xref:System.IDisposable> , de sorte `Dispose` que la méthode doit être appelée une fois que l’instance du simulateur n’est plus utilisée.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="cfa8e-110">La meilleure façon de procéder consiste à encapsuler le simulateur dans une `using` instruction, comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="cfa8e-111">Seed</span><span class="sxs-lookup"><span data-stu-id="cfa8e-111">Seed</span></span>

<span data-ttu-id="cfa8e-112">`QuantumSimulator`Utilise un générateur de nombres aléatoires pour simuler le caractère aléatoire du quantum.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="cfa8e-113">À des fins de test, il est parfois utile d’avoir des résultats déterministes.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="cfa8e-114">Pour ce faire, vous pouvez fournir une valeur de départ pour le générateur de nombres aléatoires dans le `QuantumSimulator` constructeur de à l’aide du `randomNumberGeneratorSeed` paramètre :</span><span class="sxs-lookup"><span data-stu-id="cfa8e-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="cfa8e-115">Threads</span><span class="sxs-lookup"><span data-stu-id="cfa8e-115">Threads</span></span>

<span data-ttu-id="cfa8e-116">`QuantumSimulator`Utilise [OpenMP](http://www.openmp.org/) pour paralléliser l’algèbre linéaire requis.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="cfa8e-117">Par défaut, OpenMP utilise tous les threads matériels disponibles, ce qui signifie que les programmes avec un petit nombre de qubits s’exécutent souvent lentement, car la coordination nécessaire va prendre le pas sur le travail réel.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="cfa8e-118">Cela peut être résolu en affectant à la variable `OMP_NUM_THREADS` d’environnement un nombre réduit.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="cfa8e-119">En règle générale, 1 thread convient pour jusqu’à environ 4 qubits, puis un thread supplémentaire par qubit convient, bien que cela dépende fortement de votre algorithme.</span><span class="sxs-lookup"><span data-stu-id="cfa8e-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

