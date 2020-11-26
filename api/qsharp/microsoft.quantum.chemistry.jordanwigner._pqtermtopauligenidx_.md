---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 7f1794f9e46323ccf722407fb7ae82f73ed76e40
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215433"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="a0bc4-102">_PQTermToPauliGenIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="a0bc4-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="a0bc4-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a0bc4-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a0bc4-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a0bc4-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a0bc4-105">Convertit un GeneratorIndex décrivant un terme PQ en une expression « GeneratorIndex [] » en termes de Paulis</span><span class="sxs-lookup"><span data-stu-id="a0bc4-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="a0bc4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a0bc4-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a0bc4-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a0bc4-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a0bc4-108">`GeneratorIndex` représentant un terme PQ.</span><span class="sxs-lookup"><span data-stu-id="a0bc4-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="a0bc4-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="a0bc4-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="a0bc4-110">« GeneratorIndex [] » exprimant le terme PQ en tant que termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="a0bc4-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>