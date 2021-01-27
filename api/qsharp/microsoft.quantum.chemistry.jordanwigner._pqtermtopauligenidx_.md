---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 046b3b7b78cee7f046607277896100e20c33a32d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839309"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="d2aca-102">_PQTermToPauliGenIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="d2aca-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="d2aca-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d2aca-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d2aca-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d2aca-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="d2aca-105">Convertit un GeneratorIndex décrivant un terme PQ en une expression « GeneratorIndex [] » en termes de Paulis</span><span class="sxs-lookup"><span data-stu-id="d2aca-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="d2aca-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d2aca-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="d2aca-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="d2aca-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="d2aca-108">`GeneratorIndex` représentant un terme PQ.</span><span class="sxs-lookup"><span data-stu-id="d2aca-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="d2aca-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="d2aca-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="d2aca-110">« GeneratorIndex [] » exprimant le terme PQ en tant que termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="d2aca-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>