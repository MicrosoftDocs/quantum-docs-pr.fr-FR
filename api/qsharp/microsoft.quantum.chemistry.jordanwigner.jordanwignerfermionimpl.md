---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: Opération JordanWignerFermionImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 616174d4d7f5ac8f4cea9454098d819468076648
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703198"
---
# <a name="jordanwignerfermionimpl-operation"></a><span data-ttu-id="27ebe-102">Opération JordanWignerFermionImpl</span><span class="sxs-lookup"><span data-stu-id="27ebe-102">JordanWignerFermionImpl operation</span></span>

<span data-ttu-id="27ebe-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="27ebe-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="27ebe-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27ebe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27ebe-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="27ebe-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="27ebe-106">Pour plus d’informations, consultez [modélisation de générateurs dynamiques](../libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="27ebe-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="27ebe-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="27ebe-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="27ebe-108">generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="27ebe-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="27ebe-109">Index de générateur à représenter comme évolution unitaire dans le JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="27ebe-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="27ebe-110">Procédure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27ebe-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27ebe-111">Multiplicateur sur la durée de l’évolution par rapport au terme référencé dans `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="27ebe-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="27ebe-112">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="27ebe-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="27ebe-113">Inscrivez-vous sur l’opérateur Time-Evolution.</span><span class="sxs-lookup"><span data-stu-id="27ebe-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27ebe-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27ebe-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

