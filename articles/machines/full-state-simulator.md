---
title: Simulateur d’état complet du kit de développement quantique | Microsoft Docs
description: Vue d’ensemble du simulateur d’état complet du kit de développement quantique de Microsoft
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184676"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="6da80-103">Simulateur d’état complet du kit de développement quantique</span><span class="sxs-lookup"><span data-stu-id="6da80-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="6da80-104">Le kit de développement quantum fournit un simulateur Quantum d’état complet similaire à [liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="6da80-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="6da80-105">Ce simulateur peut être utilisé pour exécuter et déboguer des algorithmes de Quantum écrits en Q # sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6da80-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="6da80-106">Ce simulateur Quantum est exposé via la classe `QuantumSimulator`.</span><span class="sxs-lookup"><span data-stu-id="6da80-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="6da80-107">Pour utiliser le simulateur, il vous suffit de créer une instance de cette classe et de la passer à la méthode `Run` de l’opération Quantum que vous souhaitez exécuter avec le reste des paramètres :</span><span class="sxs-lookup"><span data-stu-id="6da80-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="6da80-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="6da80-108">IDisposable</span></span>

<span data-ttu-id="6da80-109">La classe `QuantumSimulator` implémente <xref:System.IDisposable>. par conséquent, la méthode `Dispose` doit être appelée une fois que l’instance du simulateur n’est plus utilisée.</span><span class="sxs-lookup"><span data-stu-id="6da80-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="6da80-110">La meilleure façon de procéder consiste à encapsuler le simulateur dans une instruction `using`, comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="6da80-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="6da80-111">Initiales</span><span class="sxs-lookup"><span data-stu-id="6da80-111">Seed</span></span>

<span data-ttu-id="6da80-112">L' `QuantumSimulator` utilise un générateur de nombres aléatoires pour simuler le caractère aléatoire du quantum.</span><span class="sxs-lookup"><span data-stu-id="6da80-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="6da80-113">À des fins de test, il est parfois utile d’avoir des résultats déterministes.</span><span class="sxs-lookup"><span data-stu-id="6da80-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="6da80-114">Pour ce faire, vous pouvez fournir une valeur de départ pour le générateur de nombres aléatoires dans le constructeur de `QuantumSimulator`via le paramètre `randomNumberGeneratorSeed` :</span><span class="sxs-lookup"><span data-stu-id="6da80-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="6da80-115">Threads</span><span class="sxs-lookup"><span data-stu-id="6da80-115">Threads</span></span>

<span data-ttu-id="6da80-116">L' `QuantumSimulator` utilise [OpenMP](http://www.openmp.org/) pour paralléliser l’algèbre linéaire requis.</span><span class="sxs-lookup"><span data-stu-id="6da80-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="6da80-117">Par défaut, OpenMP utilise tous les threads matériels disponibles, ce qui signifie que les programmes avec un petit nombre de qubits s’exécutent souvent lentement, car la coordination requise va expirer le travail réel.</span><span class="sxs-lookup"><span data-stu-id="6da80-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="6da80-118">Vous pouvez résoudre ce problème en définissant la variable d’environnement `OMP_NUM_THREADS` sur un petit nombre.</span><span class="sxs-lookup"><span data-stu-id="6da80-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="6da80-119">En règle générale, 1 thread est parfait pour environ 4 qubits, et un thread supplémentaire par qubit est parfait, bien que cela dépende fortement de votre algorithme.</span><span class="sxs-lookup"><span data-stu-id="6da80-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

