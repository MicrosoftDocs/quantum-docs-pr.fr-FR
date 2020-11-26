---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203941"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="30197-102">_ComputeJordanWignerBitString fonction)</span><span class="sxs-lookup"><span data-stu-id="30197-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="30197-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="30197-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="30197-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="30197-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="30197-105">Calcule le composant Z de Jordanie – chaîne Wigner entre les index fermion dans un opérateur fermionic avec un nombre pair d’opérateurs de création/annihilation.</span><span class="sxs-lookup"><span data-stu-id="30197-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="30197-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="30197-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="30197-107">nFermions : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="30197-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="30197-108">Nombre de fermions dans le système.</span><span class="sxs-lookup"><span data-stu-id="30197-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="30197-109">idxFermions : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="30197-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="30197-110">indices d’opérateur fermionic.</span><span class="sxs-lookup"><span data-stu-id="30197-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="30197-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="30197-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="30197-112">Bitstring `Bool[]` `true` où un `PauliZ` doit être appliqué.</span><span class="sxs-lookup"><span data-stu-id="30197-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>