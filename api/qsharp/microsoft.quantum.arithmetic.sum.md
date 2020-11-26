---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Opération sum
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: 7758e29c9f08f4d05253defbe5a43a5316289522
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221791"
---
# <a name="sum-operation"></a><span data-ttu-id="2067d-102">Opération sum</span><span class="sxs-lookup"><span data-stu-id="2067d-102">Sum operation</span></span>

<span data-ttu-id="2067d-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2067d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2067d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2067d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2067d-105">Implémente une porte de somme réversible.</span><span class="sxs-lookup"><span data-stu-id="2067d-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="2067d-106">À partir d’un bit de transport encodé dans qubit `carryIn` et de deux bits opérande encodés dans `summand1` et `summand2` , calcule l’opération de bits XOR de `carryIn` `summand1` et `summand2` dans le qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="2067d-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2067d-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="2067d-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="2067d-108">Port : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2067d-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2067d-109">Qubit de transport.</span><span class="sxs-lookup"><span data-stu-id="2067d-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="2067d-110">summand1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2067d-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2067d-111">Premier opérande qubit.</span><span class="sxs-lookup"><span data-stu-id="2067d-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="2067d-112">summand2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2067d-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2067d-113">Le deuxième opérande qubit, est remplacé par le bit inférieur de la somme de `summand1` et `summand2` .</span><span class="sxs-lookup"><span data-stu-id="2067d-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2067d-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2067d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2067d-115">Notes</span><span class="sxs-lookup"><span data-stu-id="2067d-115">Remarks</span></span>

<span data-ttu-id="2067d-116">Contrairement à l' `Carry` opération, cela ne calcule pas le bit de report.</span><span class="sxs-lookup"><span data-stu-id="2067d-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>