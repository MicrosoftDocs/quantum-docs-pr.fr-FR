---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Opération sum
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706198"
---
# <a name="sum-operation"></a><span data-ttu-id="fec3a-102">Opération sum</span><span class="sxs-lookup"><span data-stu-id="fec3a-102">Sum operation</span></span>

<span data-ttu-id="fec3a-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fec3a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fec3a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fec3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fec3a-105">Implémente une porte de somme réversible.</span><span class="sxs-lookup"><span data-stu-id="fec3a-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="fec3a-106">À partir d’un bit de transport encodé dans qubit `carryIn` et de deux bits opérande encodés dans `summand1` et `summand2` , calcule l’opération de bits XOR de `carryIn` `summand1` et `summand2` dans le qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="fec3a-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="fec3a-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="fec3a-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="fec3a-108">Port : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fec3a-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fec3a-109">Qubit de transport.</span><span class="sxs-lookup"><span data-stu-id="fec3a-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="fec3a-110">summand1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fec3a-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fec3a-111">Premier opérande qubit.</span><span class="sxs-lookup"><span data-stu-id="fec3a-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="fec3a-112">summand2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fec3a-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fec3a-113">Le deuxième opérande qubit, est remplacé par le bit inférieur de la somme de `summand1` et `summand2` .</span><span class="sxs-lookup"><span data-stu-id="fec3a-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fec3a-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fec3a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fec3a-115">Notes</span><span class="sxs-lookup"><span data-stu-id="fec3a-115">Remarks</span></span>

<span data-ttu-id="fec3a-116">Contrairement à l' `Carry` opération, cela ne calcule pas le bit de report.</span><span class="sxs-lookup"><span data-stu-id="fec3a-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>