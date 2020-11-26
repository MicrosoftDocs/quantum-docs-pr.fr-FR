---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: fc5ad0e97374c52a90012b0ce633af8488f3ad88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215093"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="963a0-102">_V0123TermToPauliGenIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="963a0-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="963a0-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="963a0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="963a0-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="963a0-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="963a0-105">Convertit un GeneratorIndex décrivant un terme PQRS en une expression’GeneratorIndex [] 'en termes de Paulis</span><span class="sxs-lookup"><span data-stu-id="963a0-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="963a0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="963a0-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="963a0-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="963a0-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="963a0-108">`GeneratorIndex` représentant un terme PQRS.</span><span class="sxs-lookup"><span data-stu-id="963a0-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="963a0-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="963a0-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="963a0-110">'GeneratorIndex [] 'exprimant le terme PQRS en tant que termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="963a0-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>