---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Opération PauliEvolutionImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 2fc9fda2dd6eec71d8b17ba8a00d8545e517eec8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706667"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="3f0ea-102">Opération PauliEvolutionImpl</span><span class="sxs-lookup"><span data-stu-id="3f0ea-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="3f0ea-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3f0ea-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3f0ea-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f0ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f0ea-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de Pauli.</span><span class="sxs-lookup"><span data-stu-id="3f0ea-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="3f0ea-106">Pour plus d’informations, consultez [modélisation de générateurs dynamiques](/quantum/libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="3f0ea-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3f0ea-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="3f0ea-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="3f0ea-108">generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3f0ea-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3f0ea-109">Index du générateur à représenter en tant qu’évolution unitaire dans la base Pauli.</span><span class="sxs-lookup"><span data-stu-id="3f0ea-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="3f0ea-110">Delta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f0ea-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f0ea-111">Multiplicateur sur la durée de l’évolution par rapport au terme référencé dans `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="3f0ea-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3f0ea-112">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f0ea-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f0ea-113">Inscrivez-vous sur l’opérateur Time-Evolution.</span><span class="sxs-lookup"><span data-stu-id="3f0ea-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f0ea-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f0ea-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

