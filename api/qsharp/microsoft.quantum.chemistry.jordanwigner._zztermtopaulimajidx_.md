---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _ZZTermToPauliMajIdx_ fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: ca713260da2dd717cb1548ef86b7faa0d1b826aa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214923"
---
# <a name="_zztermtopaulimajidx_-function"></a><span data-ttu-id="d5a68-102">_ZZTermToPauliMajIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="d5a68-102">_ZZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="d5a68-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d5a68-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d5a68-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d5a68-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="d5a68-105">Convertit un GeneratorIndex décrivant un terme ZZ en expression « GeneratorIndex [] » en termes de Paulis.</span><span class="sxs-lookup"><span data-stu-id="d5a68-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="d5a68-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d5a68-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="d5a68-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="d5a68-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="d5a68-108">`GeneratorIndex` représentant un terme ZZ.</span><span class="sxs-lookup"><span data-stu-id="d5a68-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="d5a68-109">Sortie : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="d5a68-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="d5a68-110">'GeneratorIndex [] 'exprimant le terme ZZ comme termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="d5a68-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>