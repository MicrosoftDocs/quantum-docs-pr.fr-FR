---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Opération PauliEvolutionImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 1c588c225cb7c91830e986c7eca9b9fafd445d4e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847942"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="f1c59-102">Opération PauliEvolutionImpl</span><span class="sxs-lookup"><span data-stu-id="f1c59-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="f1c59-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f1c59-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f1c59-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1c59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1c59-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de Pauli.</span><span class="sxs-lookup"><span data-stu-id="f1c59-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="f1c59-106">Pour plus d’informations, consultez [modélisation de générateurs dynamiques](/quantum/libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="f1c59-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f1c59-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="f1c59-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="f1c59-108">generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f1c59-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f1c59-109">Index du générateur à représenter en tant qu’évolution unitaire dans la base Pauli.</span><span class="sxs-lookup"><span data-stu-id="f1c59-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="f1c59-110">Delta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f1c59-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f1c59-111">Multiplicateur sur la durée de l’évolution par rapport au terme référencé dans `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="f1c59-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f1c59-112">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f1c59-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f1c59-113">Inscrivez-vous sur l’opérateur Time-Evolution.</span><span class="sxs-lookup"><span data-stu-id="f1c59-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1c59-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1c59-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

