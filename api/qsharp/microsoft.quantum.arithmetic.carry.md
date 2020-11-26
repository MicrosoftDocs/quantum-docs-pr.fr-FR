---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Opération de transport
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223593"
---
# <a name="carry-operation"></a><span data-ttu-id="0fef9-102">Opération de transport</span><span class="sxs-lookup"><span data-stu-id="0fef9-102">Carry operation</span></span>

<span data-ttu-id="0fef9-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0fef9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0fef9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0fef9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0fef9-105">Implémente une porte de transport réversible.</span><span class="sxs-lookup"><span data-stu-id="0fef9-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="0fef9-106">Avec un bit de transport encodé dans qubit `carryIn` et deux bits opérande encodés dans `summand1` et `summand2` , calcule le XOR au niveau du bit de `carryIn` et `summand1` `summand2` dans le qubit `summand2` et le résultat est XOR au qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="0fef9-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0fef9-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="0fef9-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="0fef9-108">Port : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0fef9-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0fef9-109">Qubit de transport.</span><span class="sxs-lookup"><span data-stu-id="0fef9-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="0fef9-110">summand1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0fef9-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0fef9-111">Premier opérande qubit.</span><span class="sxs-lookup"><span data-stu-id="0fef9-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="0fef9-112">summand2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0fef9-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0fef9-113">Le deuxième opérande qubit, est remplacé par le bit inférieur de la somme de `summand1` et `summand2` .</span><span class="sxs-lookup"><span data-stu-id="0fef9-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="0fef9-114">carryOut : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0fef9-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0fef9-115">Procédez à la qubit, sera XOR avec le bit le plus élevé de la somme.</span><span class="sxs-lookup"><span data-stu-id="0fef9-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0fef9-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0fef9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

