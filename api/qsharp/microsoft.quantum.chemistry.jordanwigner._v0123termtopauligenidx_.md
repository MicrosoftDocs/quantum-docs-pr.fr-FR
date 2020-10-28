---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b522691d6826933122e2ebac051b15e35b9902e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703282"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="a6ab2-102">_V0123TermToPauliGenIdx_ fonction)</span><span class="sxs-lookup"><span data-stu-id="a6ab2-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="a6ab2-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a6ab2-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a6ab2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6ab2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6ab2-105">Convertit un GeneratorIndex décrivant un terme PQRS en une expression’GeneratorIndex [] 'en termes de Paulis</span><span class="sxs-lookup"><span data-stu-id="a6ab2-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="a6ab2-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a6ab2-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a6ab2-107">terme : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a6ab2-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a6ab2-108">`GeneratorIndex` représentant un terme PQRS.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="a6ab2-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="a6ab2-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="a6ab2-110">'GeneratorIndex [] 'exprimant le terme PQRS en tant que termes Pauli.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>