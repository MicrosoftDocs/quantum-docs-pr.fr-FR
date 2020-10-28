---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: d2d916655b7538b39d5739d67dbb3fc9920cf67a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707853"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a><span data-ttu-id="b35e0-102">JordanWignerOptimizedFermionEvolutionSet fonction)</span><span class="sxs-lookup"><span data-stu-id="b35e0-102">JordanWignerOptimizedFermionEvolutionSet function</span></span>

<span data-ttu-id="b35e0-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b35e0-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="b35e0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b35e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b35e0-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de Pauli.</span><span class="sxs-lookup"><span data-stu-id="b35e0-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a><span data-ttu-id="b35e0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b35e0-106">Input</span></span>

### <a name="parityqubit--qubit"></a><span data-ttu-id="b35e0-107">parityQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b35e0-107">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b35e0-108">Qubit qui détermine le signe de l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="b35e0-108">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionset"></a><span data-ttu-id="b35e0-109">Sortie : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="b35e0-109">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="b35e0-110">`EvolutionSet`Qui mappe un `GeneratorIndex` pour la base JWOptimized à un’EvolutionUnitary.</span><span class="sxs-lookup"><span data-stu-id="b35e0-110">An `EvolutionSet` that maps a `GeneratorIndex` for the JWOptimized basis to an \`EvolutionUnitary.</span></span>