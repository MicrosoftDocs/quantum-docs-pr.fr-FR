---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703495"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="cb742-102">_ComputeJordanWignerBitString fonction)</span><span class="sxs-lookup"><span data-stu-id="cb742-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="cb742-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="cb742-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="cb742-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb742-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb742-105">Calcule le composant Z de Jordanie – chaîne Wigner entre les index fermion dans un opérateur fermionic avec un nombre pair d’opérateurs de création/annihilation.</span><span class="sxs-lookup"><span data-stu-id="cb742-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="cb742-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="cb742-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="cb742-107">nFermions : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb742-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cb742-108">Nombre de fermions dans le système.</span><span class="sxs-lookup"><span data-stu-id="cb742-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="cb742-109">idxFermions : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cb742-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cb742-110">indices d’opérateur fermionic.</span><span class="sxs-lookup"><span data-stu-id="cb742-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cb742-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="cb742-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="cb742-112">Bitstring `Bool[]` `true` où un `PauliZ` doit être appliqué.</span><span class="sxs-lookup"><span data-stu-id="cb742-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>