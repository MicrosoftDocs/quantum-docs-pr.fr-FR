---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: _PQTermToPauliMajIdx_ fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: bb9fad038c30b3362ffbecf546bcf85cb7dd13df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215399"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="88606-102">_PQTermToPauliMajIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="88606-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="88606-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="88606-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="88606-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="88606-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="88606-105">Convertit un GeneratorIndex décrivant un terme PQ en une expression « GeneratorIndex [] » en termes de Paulis</span><span class="sxs-lookup"><span data-stu-id="88606-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="88606-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="88606-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="88606-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="88606-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="88606-108">`GeneratorIndex` représentant un terme PQ.</span><span class="sxs-lookup"><span data-stu-id="88606-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="88606-109">Sortie : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="88606-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="88606-110">« GeneratorIndex [] » exprimant le terme PQ en tant que termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="88606-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>