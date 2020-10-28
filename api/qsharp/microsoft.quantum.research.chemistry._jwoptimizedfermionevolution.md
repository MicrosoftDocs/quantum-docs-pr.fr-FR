---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: Opération de _JWOptimizedFermionEvolution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5976b65d44c0e8597088dbaa6b85ffde634edcdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708135"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="48755-102">Opération de _JWOptimizedFermionEvolution</span><span class="sxs-lookup"><span data-stu-id="48755-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="48755-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="48755-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="48755-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48755-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48755-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="48755-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="48755-106">Pour plus d’informations, consultez [modélisation de générateurs dynamiques](../libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="48755-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="48755-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="48755-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="48755-108">generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="48755-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="48755-109">Index du générateur à représenter en tant qu’évolution unitaire dans la base JWOptimized.</span><span class="sxs-lookup"><span data-stu-id="48755-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="48755-110">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48755-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="48755-111">Multiplicateur sur la durée de l’évolution par rapport au terme référencé dans `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="48755-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="48755-112">parityQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="48755-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="48755-113">Qubit qui détermine le signe de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="48755-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="48755-114">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="48755-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="48755-115">Inscrivez-vous sur l’opérateur Time-Evolution.</span><span class="sxs-lookup"><span data-stu-id="48755-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48755-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48755-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

