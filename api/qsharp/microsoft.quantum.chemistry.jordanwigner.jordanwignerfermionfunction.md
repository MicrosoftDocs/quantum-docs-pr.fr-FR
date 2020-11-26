---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: e1eeed0dcd4084401e2680ff1188db4225ee85ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214753"
---
# <a name="jordanwignerfermionfunction-function"></a><span data-ttu-id="6d142-102">JordanWignerFermionFunction fonction)</span><span class="sxs-lookup"><span data-stu-id="6d142-102">JordanWignerFermionFunction function</span></span>

<span data-ttu-id="6d142-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="6d142-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="6d142-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6d142-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6d142-105">Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="6d142-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="6d142-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6d142-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="6d142-107">generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6d142-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6d142-108">Index de générateur à représenter comme évolution unitaire dans le JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="6d142-108">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="6d142-109">Sortie : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="6d142-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="6d142-110">`EvolutionUnitary`Représentant l’évolution temporelle du terme référencé dans’generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="6d142-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>