---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: _ZTermToPauliGenIdx fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: f4643ef03a0178f2c3ba1ea68f36f2f3fcd7b9ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215025"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="86109-102">_ZTermToPauliGenIdx fonction)</span><span class="sxs-lookup"><span data-stu-id="86109-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="86109-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="86109-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="86109-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="86109-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="86109-105">Convertit un GeneratorIndex décrivant un terme Z en une expression « GeneratorIndex [] » en termes de Paulis.</span><span class="sxs-lookup"><span data-stu-id="86109-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="86109-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="86109-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="86109-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="86109-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="86109-108">`GeneratorIndex` représentant un terme Z.</span><span class="sxs-lookup"><span data-stu-id="86109-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="86109-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="86109-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="86109-110">« GeneratorIndex [] » exprimant Z term comme termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="86109-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>