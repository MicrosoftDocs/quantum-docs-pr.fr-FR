---
title: Kit de développement quantique Toffoli Simulator | Microsoft Docs
description: Vue d’ensemble du simulateur Toffoli du kit de développement quantique de Microsoft
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442356"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="a0185-103">Simulateur Toffoli du kit de développement quantique</span><span class="sxs-lookup"><span data-stu-id="a0185-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="a0185-104">Le kit de développement quantum fournit un simulateur Toffoli, qui est un simulateur spécialisé qui peut simuler des algorithmes Quantum qui sont limités aux opérations de Quantum x, CNOTIN et multi-contrôlés X (toutes les calculs et logiques classiques sont disponibles).</span><span class="sxs-lookup"><span data-stu-id="a0185-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="a0185-105">Alors que le simulateur Toffoli est beaucoup plus limité en fonctionnement que le [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), il peut simuler beaucoup plus de qubits.</span><span class="sxs-lookup"><span data-stu-id="a0185-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="a0185-106">Le simulateur Toffoli peut être utilisé avec des millions de qubits, tandis que le simulateur d’état complet est généralement limité à environ 30.</span><span class="sxs-lookup"><span data-stu-id="a0185-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="a0185-107">Il peut exécuter et déboguer un ensemble limité d’algorithmes de Quantum écrits en Q # sur votre ordinateur ; par exemple, les Oracle qui évaluent des fonctions booléennes peuvent être implémentées à l’aide de ces portes et, par conséquent, testées sur la variation d’un grand nombre de qubits utilisant ce simulateur.</span><span class="sxs-lookup"><span data-stu-id="a0185-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="a0185-108">Ce simulateur Quantum est exposé via la classe `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="a0185-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="a0185-109">Pour utiliser le simulateur, il vous suffit de créer une instance de cette classe et de la passer à la méthode `Run` de l’opération Quantum que vous souhaitez exécuter avec le reste des paramètres :</span><span class="sxs-lookup"><span data-stu-id="a0185-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="a0185-110">Autres opérations</span><span class="sxs-lookup"><span data-stu-id="a0185-110">Other Operations</span></span>

<span data-ttu-id="a0185-111">Le `ToffoliSimulator` prend en charge les rotations et élever Paulis, comme `R` et `Exp`, lorsque l’opération obtenue est égale à `X` ou à l’identité.</span><span class="sxs-lookup"><span data-stu-id="a0185-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="a0185-112">Les mesures et les Assert sont pris en charge, mais uniquement dans la base Pauli `Z`.</span><span class="sxs-lookup"><span data-stu-id="a0185-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="a0185-113">Notez que la probabilité d’une mesure est toujours 0 ou 1 ; Il n’y a pas de caractère aléatoire dans le simulateur Toffoli.</span><span class="sxs-lookup"><span data-stu-id="a0185-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="a0185-114">`DumpMachine` et `DumpRegister` sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a0185-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="a0185-115">Ils génèrent tous deux un état de base `Z`actuel de chaque qubit, un qubit par ligne.</span><span class="sxs-lookup"><span data-stu-id="a0185-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="a0185-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="a0185-116">QubitCount</span></span>

<span data-ttu-id="a0185-117">Par défaut, le `ToffoliSimulator` alloue de l’espace pour 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="a0185-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="a0185-118">Si votre algorithme en requiert plus, vous pouvez modifier le nombre de qubit en fournissant une valeur pour le paramètre `qubitCount` au constructeur.</span><span class="sxs-lookup"><span data-stu-id="a0185-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="a0185-119">Chaque qubit supplémentaire requiert un octet de mémoire supplémentaire, donc il n’y a pas de coût significatif pour le surestimation du nombre de qubits dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="a0185-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="a0185-120">Exemple :</span><span class="sxs-lookup"><span data-stu-id="a0185-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
