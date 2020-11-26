---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 13897d831bc3382dbb23b653c5905978330eb622
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214991"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="65ce1-102">_ZTermToPauliMajIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="65ce1-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="65ce1-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="65ce1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="65ce1-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="65ce1-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="65ce1-105">Convertit un GeneratorIndex décrivant un terme Z en une expression « GeneratorIndex [] » en termes de Paulis.</span><span class="sxs-lookup"><span data-stu-id="65ce1-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="65ce1-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="65ce1-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="65ce1-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="65ce1-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="65ce1-108">`GeneratorIndex` représentant un terme Z.</span><span class="sxs-lookup"><span data-stu-id="65ce1-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="65ce1-109">Sortie : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="65ce1-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="65ce1-110">« GeneratorIndex [] » exprimant Z term comme termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="65ce1-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>