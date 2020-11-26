---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: _ZZTermToPauliGenIdx fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 01f4ebf4f2acc0fd76ae101e0c511cd70b03fada
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214957"
---
# <a name="_zztermtopauligenidx-function"></a><span data-ttu-id="24a3a-102">_ZZTermToPauliGenIdx fonction)</span><span class="sxs-lookup"><span data-stu-id="24a3a-102">_ZZTermToPauliGenIdx function</span></span>

<span data-ttu-id="24a3a-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="24a3a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="24a3a-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="24a3a-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="24a3a-105">Convertit un GeneratorIndex décrivant un terme ZZ en expression « GeneratorIndex [] » en termes de Paulis.</span><span class="sxs-lookup"><span data-stu-id="24a3a-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="24a3a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="24a3a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="24a3a-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="24a3a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="24a3a-108">`GeneratorIndex` représentant un terme ZZ.</span><span class="sxs-lookup"><span data-stu-id="24a3a-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="24a3a-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="24a3a-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="24a3a-110">'GeneratorIndex [] 'exprimant le terme ZZ comme termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="24a3a-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>