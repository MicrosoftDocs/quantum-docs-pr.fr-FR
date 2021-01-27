---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Opération sum
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847750"
---
# <a name="sum-operation"></a><span data-ttu-id="a82ef-102">Opération sum</span><span class="sxs-lookup"><span data-stu-id="a82ef-102">Sum operation</span></span>

<span data-ttu-id="a82ef-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a82ef-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a82ef-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a82ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a82ef-105">Implémente une porte de somme réversible.</span><span class="sxs-lookup"><span data-stu-id="a82ef-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="a82ef-106">À partir d’un bit de transport encodé dans qubit `carryIn` et de deux bits opérande encodés dans `summand1` et `summand2` , calcule l’opération de bits XOR de `carryIn` `summand1` et `summand2` dans le qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="a82ef-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a82ef-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="a82ef-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="a82ef-108">Port : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a82ef-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a82ef-109">Qubit de transport.</span><span class="sxs-lookup"><span data-stu-id="a82ef-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="a82ef-110">summand1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a82ef-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a82ef-111">Premier opérande qubit.</span><span class="sxs-lookup"><span data-stu-id="a82ef-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="a82ef-112">summand2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a82ef-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a82ef-113">Le deuxième opérande qubit, est remplacé par le bit inférieur de la somme de `summand1` et `summand2` .</span><span class="sxs-lookup"><span data-stu-id="a82ef-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a82ef-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a82ef-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a82ef-115">Notes</span><span class="sxs-lookup"><span data-stu-id="a82ef-115">Remarks</span></span>

<span data-ttu-id="a82ef-116">Contrairement à l' `Carry` opération, cela ne calcule pas le bit de report.</span><span class="sxs-lookup"><span data-stu-id="a82ef-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>