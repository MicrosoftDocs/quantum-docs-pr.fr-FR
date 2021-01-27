---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: _PQTermToPauliMajIdx_ fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: edb9302e04de2abc6dfa9da0da27504f776e721f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839287"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="6b68b-102">_PQTermToPauliMajIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="6b68b-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="6b68b-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="6b68b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="6b68b-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6b68b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6b68b-105">Convertit un GeneratorIndex décrivant un terme PQ en une expression « GeneratorIndex [] » en termes de Paulis</span><span class="sxs-lookup"><span data-stu-id="6b68b-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="6b68b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6b68b-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="6b68b-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6b68b-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6b68b-108">`GeneratorIndex` représentant un terme PQ.</span><span class="sxs-lookup"><span data-stu-id="6b68b-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="6b68b-109">Sortie : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="6b68b-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="6b68b-110">« GeneratorIndex [] » exprimant le terme PQ en tant que termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="6b68b-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>