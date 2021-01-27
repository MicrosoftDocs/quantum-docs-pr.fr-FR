---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Opération ApplyTransposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855577"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="0f9b7-102">Opération ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="0f9b7-102">ApplyTransposition operation</span></span>

<span data-ttu-id="0f9b7-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0f9b7-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0f9b7-105">Description</span><span class="sxs-lookup"><span data-stu-id="0f9b7-105">Description</span></span>

<span data-ttu-id="0f9b7-106">Cette opération permute l’amplitude au niveau de l’index `a` avec l’amplitude à `b` l’index dans le vecteur d’État donné de `register` longueur $n $.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="0f9b7-107">Si est `a` égal `b` à, le vecteur d’État n’est pas modifié.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="0f9b7-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="0f9b7-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="0f9b7-109">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f9b7-110">Premier index (doit être une valeur comprise entre 0 et $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="0f9b7-111">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f9b7-112">Second index (doit être une valeur comprise entre 0 et $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="0f9b7-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f9b7-114">Liste de $n $ qubits à laquelle la transposition est appliquée.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f9b7-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="0f9b7-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="0f9b7-116">Example</span></span>

<span data-ttu-id="0f9b7-117">Préparez une superposition uniforme de nombre États $ | 1 \ rangle $, $ | 2 \ rangle $ et $ | 3 \ rangle $ sur 2 qubits.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```