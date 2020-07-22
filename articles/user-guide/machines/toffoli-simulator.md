---
title: Simulateur Quantum Toffoli-Kit de développement quantique
description: Découvrez Microsoft QDK Toffoli Simulator, un simulateur Quantum spécial qui peut être utilisé avec des millions de qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870615"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="24484-103">QDK (Quantum Development Kit) Toffoli Simulator</span><span class="sxs-lookup"><span data-stu-id="24484-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="24484-104">Le simulateur QDK Toffoli est un simulateur à usage spécial avec une étendue limitée et prend en charge uniquement les `X` `CNOT` opérations de Quantum, et multiples `X` .</span><span class="sxs-lookup"><span data-stu-id="24484-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="24484-105">Toute la logique et les calculs classiques sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="24484-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="24484-106">Alors que le simulateur Toffoli est plus limité en termes de fonctionnalités que le [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), il présente l’avantage de pouvoir simuler beaucoup plus de qubits.</span><span class="sxs-lookup"><span data-stu-id="24484-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="24484-107">Le simulateur Toffoli peut être utilisé avec des millions de qubits, tandis que le simulateur d’état complet est limité à environ 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="24484-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="24484-108">Cela est utile, par exemple, avec Oracle qui évaluent des fonctions booléennes : elles peuvent être implémentées à l’aide de l’ensemble limité d’algorithmes pris en charge et testés sur un grand nombre de qubits.</span><span class="sxs-lookup"><span data-stu-id="24484-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="24484-109">Appel du simulateur Toffoli</span><span class="sxs-lookup"><span data-stu-id="24484-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="24484-110">Vous exposez le simulateur Toffoli par le biais de la `ToffoliSimulator` classe.</span><span class="sxs-lookup"><span data-stu-id="24484-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="24484-111">Pour plus d’informations, consultez [méthodes d’exécution d’un programme Q #](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="24484-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="24484-112">Appel du simulateur Toffoli à partir de C #</span><span class="sxs-lookup"><span data-stu-id="24484-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="24484-113">Comme pour les autres ordinateurs cibles, vous créez d’abord une instance de la `ToffoliSimulator` classe, puis vous la transmettez comme premier paramètre de la méthode d’une opération `Run` .</span><span class="sxs-lookup"><span data-stu-id="24484-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="24484-114">Notez que, contrairement `QuantumSimulator` à la classe, la `ToffoliSimulator` classe n’implémente pas l' <xref:System.IDisposable> interface, ce qui signifie que vous n’avez pas besoin de la placer dans une `using` instruction.</span><span class="sxs-lookup"><span data-stu-id="24484-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="24484-115">Appel du simulateur Toffoli à partir de Python</span><span class="sxs-lookup"><span data-stu-id="24484-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="24484-116">Utilisez la méthode [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) à partir de la bibliothèque Python avec l’opération Q # importée :</span><span class="sxs-lookup"><span data-stu-id="24484-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="24484-117">Appel du simulateur Toffoli à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="24484-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="24484-118">Quand vous exécutez un programme Q # à partir de la ligne de commande, utilisez le paramètre **--simulateur** (ou **-s** raccourci) pour spécifier l’ordinateur cible du simulateur Toffoli.</span><span class="sxs-lookup"><span data-stu-id="24484-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="24484-119">La commande suivante exécute un programme à l’aide de l’estimateur de ressources :</span><span class="sxs-lookup"><span data-stu-id="24484-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="24484-120">Appel du simulateur Toffoli à partir de blocs-notes Juptyer</span><span class="sxs-lookup"><span data-stu-id="24484-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="24484-121">Utilisez la commande IQ # Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) pour exécuter l’opération Q #.</span><span class="sxs-lookup"><span data-stu-id="24484-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="24484-122">Opérations prises en charge</span><span class="sxs-lookup"><span data-stu-id="24484-122">Supported operations</span></span>

<span data-ttu-id="24484-123">Le simulateur Toffoli prend en charge :</span><span class="sxs-lookup"><span data-stu-id="24484-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="24484-124">Les rotations et élever Paulis, comme `R` et `Exp` , lorsque l’opération obtenue est égale `X` ou la matrice d’identité.</span><span class="sxs-lookup"><span data-stu-id="24484-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="24484-125">Opérations de mesure et d' [assertion](xref:microsoft.quantum.diagnostics.assertmeasurement) , mais uniquement dans la `Z` base Pauli.</span><span class="sxs-lookup"><span data-stu-id="24484-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="24484-126">Notez que la probabilité d’une opération de mesure est toujours **égale à 0** ou **1**; Il n’y a pas de caractère aléatoire dans le simulateur Toffoli.</span><span class="sxs-lookup"><span data-stu-id="24484-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="24484-127">`DumpMachine``DumpRegister`fonctions et.</span><span class="sxs-lookup"><span data-stu-id="24484-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="24484-128">Les deux fonctions génèrent l' `Z` état actuel de chaque qubit, à raison d’un qubit par ligne.</span><span class="sxs-lookup"><span data-stu-id="24484-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="24484-129">Spécification du nombre de qubits</span><span class="sxs-lookup"><span data-stu-id="24484-129">Specifying the number of qubits</span></span>

<span data-ttu-id="24484-130">Par défaut, une `ToffoliSimulator` instance alloue de l’espace pour 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="24484-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="24484-131">Si votre algorithme requiert plus de qubits, vous pouvez spécifier le nombre de qubit en fournissant une valeur pour le `qubitCount` paramètre au constructeur.</span><span class="sxs-lookup"><span data-stu-id="24484-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="24484-132">Chaque qubit supplémentaire ne nécessitant qu’un seul octet de mémoire, il n’y a donc pas de coût significatif pour l’estimation du nombre de qubits dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="24484-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="24484-133">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="24484-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="24484-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24484-134">See also</span></span>

- [<span data-ttu-id="24484-135">Estimateur de ressources de Quantum</span><span class="sxs-lookup"><span data-stu-id="24484-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="24484-136">Simulateur de traces Quantum</span><span class="sxs-lookup"><span data-stu-id="24484-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="24484-137">Simulateur d’état complet du quantum</span><span class="sxs-lookup"><span data-stu-id="24484-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 