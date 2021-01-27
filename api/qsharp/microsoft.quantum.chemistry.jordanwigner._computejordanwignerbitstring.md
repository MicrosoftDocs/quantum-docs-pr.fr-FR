---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839530"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="ac7fb-102">_ComputeJordanWignerBitString fonction)</span><span class="sxs-lookup"><span data-stu-id="ac7fb-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="ac7fb-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ac7fb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ac7fb-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ac7fb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ac7fb-105">Calcule le composant Z de Jordanie – chaîne Wigner entre les index fermion dans un opérateur fermionic avec un nombre pair d’opérateurs de création/annihilation.</span><span class="sxs-lookup"><span data-stu-id="ac7fb-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="ac7fb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ac7fb-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="ac7fb-107">nFermions : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac7fb-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac7fb-108">Nombre de fermions dans le système.</span><span class="sxs-lookup"><span data-stu-id="ac7fb-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="ac7fb-109">idxFermions : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ac7fb-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ac7fb-110">indices d’opérateur fermionic.</span><span class="sxs-lookup"><span data-stu-id="ac7fb-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ac7fb-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ac7fb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="ac7fb-112">Bitstring `Bool[]` `true` où un `PauliZ` doit être appliqué.</span><span class="sxs-lookup"><span data-stu-id="ac7fb-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="ac7fb-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="ac7fb-113">Example</span></span>

<span data-ttu-id="ac7fb-114">Let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]); bitString est [false, false, false, true, true, true, false].</span><span class="sxs-lookup"><span data-stu-id="ac7fb-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>