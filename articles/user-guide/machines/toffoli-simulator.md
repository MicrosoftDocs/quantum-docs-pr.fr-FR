---
title: Simulateur Toffoli du kit de développement quantique
description: Découvrez Microsoft QDK Toffoli Simulator, un simulateur Quantum spécial qui peut être utilisé avec des millions de qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275147"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="c3f0b-103">Simulateur Toffoli du kit de développement quantique</span><span class="sxs-lookup"><span data-stu-id="c3f0b-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="c3f0b-104">Le kit de développement quantum fournit un simulateur Toffoli, qui est un simulateur spécialisé qui peut simuler des algorithmes Quantum qui sont limités aux opérations de Quantum x, CNOTIN et multi-contrôlés X (toutes les calculs et logiques classiques sont disponibles).</span><span class="sxs-lookup"><span data-stu-id="c3f0b-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="c3f0b-105">Alors que le simulateur Toffoli est beaucoup plus limité en fonctionnement que le [simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator), il peut simuler beaucoup plus de qubits.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="c3f0b-106">Le simulateur Toffoli peut être utilisé avec des millions de qubits, tandis que le simulateur d’état complet est généralement limité à environ 30.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="c3f0b-107">Il peut exécuter et déboguer un ensemble limité d’algorithmes de Quantum écrits en Q # sur votre ordinateur ; par exemple, les Oracle qui évaluent des fonctions booléennes peuvent être implémentées à l’aide de ces portes et, par conséquent, testées sur la variation d’un grand nombre de qubits utilisant ce simulateur.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="c3f0b-108">Ce simulateur Quantum est exposé via la `ToffoliSimulator` classe.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="c3f0b-109">Pour utiliser le simulateur, il vous suffit de créer une instance de cette classe et de la passer à la `Run` méthode de l’opération Quantum que vous souhaitez exécuter avec le reste des paramètres :</span><span class="sxs-lookup"><span data-stu-id="c3f0b-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="c3f0b-110">Autres opérations</span><span class="sxs-lookup"><span data-stu-id="c3f0b-110">Other Operations</span></span>

<span data-ttu-id="c3f0b-111">`ToffoliSimulator`Prend en charge les rotations et les élever Paulis, tels que `R` et `Exp` , lorsque l’opération obtenue est égale à `X` ou à l’identité.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="c3f0b-112">Les mesures et les Assert sont pris en charge, mais uniquement dans la `Z` base Pauli.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="c3f0b-113">Notez que la probabilité d’une mesure est toujours 0 ou 1 ; Il n’y a pas de caractère aléatoire dans le simulateur Toffoli.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="c3f0b-114">`DumpMachine`et `DumpRegister` sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="c3f0b-115">Ils génèrent tous deux l' `Z` état actuel de chaque qubit, à raison d’un qubit par ligne.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="c3f0b-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="c3f0b-116">QubitCount</span></span>

<span data-ttu-id="c3f0b-117">Par défaut, le `ToffoliSimulator` alloue de l’espace pour 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="c3f0b-118">Si votre algorithme en requiert plus, vous pouvez modifier le nombre de qubit en fournissant une valeur pour le `qubitCount` paramètre au constructeur.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="c3f0b-119">Chaque qubit supplémentaire requiert un octet de mémoire supplémentaire, donc il n’y a pas de coût significatif pour le surestimation du nombre de qubits dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="c3f0b-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="c3f0b-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c3f0b-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```