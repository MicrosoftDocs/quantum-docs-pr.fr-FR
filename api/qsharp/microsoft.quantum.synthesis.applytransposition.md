---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Opération ApplyTransposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203312"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="6027a-102">Opération ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="6027a-102">ApplyTransposition operation</span></span>

<span data-ttu-id="6027a-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6027a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6027a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6027a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6027a-105">Description</span><span class="sxs-lookup"><span data-stu-id="6027a-105">Description</span></span>

<span data-ttu-id="6027a-106">Cette opération permute l’amplitude au niveau de l’index `a` avec l’amplitude à `b` l’index dans le vecteur d’État donné de `register` longueur $n $.</span><span class="sxs-lookup"><span data-stu-id="6027a-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="6027a-107">Si est `a` égal `b` à, le vecteur d’État n’est pas modifié.</span><span class="sxs-lookup"><span data-stu-id="6027a-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="6027a-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="6027a-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6027a-109">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6027a-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6027a-110">Premier index (doit être une valeur comprise entre 0 et $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="6027a-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="6027a-111">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6027a-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6027a-112">Second index (doit être une valeur comprise entre 0 et $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="6027a-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6027a-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6027a-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6027a-114">Liste de $n $ qubits à laquelle la transposition est appliquée.</span><span class="sxs-lookup"><span data-stu-id="6027a-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6027a-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6027a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

