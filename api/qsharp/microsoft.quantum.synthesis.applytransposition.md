---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Opération ApplyTransposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709191"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="a2983-102">Opération ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="a2983-102">ApplyTransposition operation</span></span>

<span data-ttu-id="a2983-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a2983-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a2983-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2983-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="a2983-105">Description</span><span class="sxs-lookup"><span data-stu-id="a2983-105">Description</span></span>

<span data-ttu-id="a2983-106">Cette opération permute l’amplitude au niveau de l’index `a` avec l’amplitude à `b` l’index dans le vecteur d’État donné de `register` longueur $n $.</span><span class="sxs-lookup"><span data-stu-id="a2983-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="a2983-107">Si est `a` égal `b` à, le vecteur d’État n’est pas modifié.</span><span class="sxs-lookup"><span data-stu-id="a2983-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="a2983-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="a2983-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a2983-109">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a2983-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a2983-110">Premier index (doit être une valeur comprise entre 0 et $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="a2983-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="a2983-111">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a2983-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a2983-112">Second index (doit être une valeur comprise entre 0 et $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="a2983-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="a2983-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a2983-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a2983-114">Liste de $n $ qubits à laquelle la transposition est appliquée.</span><span class="sxs-lookup"><span data-stu-id="a2983-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2983-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2983-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

