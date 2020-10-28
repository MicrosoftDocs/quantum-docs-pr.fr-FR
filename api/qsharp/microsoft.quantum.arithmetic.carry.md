---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Opération de transport
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 2b977151861fb01be7d7dbad6e0a7b803fded880
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707403"
---
# <a name="carry-operation"></a><span data-ttu-id="793d8-102">Opération de transport</span><span class="sxs-lookup"><span data-stu-id="793d8-102">Carry operation</span></span>

<span data-ttu-id="793d8-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="793d8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="793d8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="793d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="793d8-105">Implémente une porte de transport réversible.</span><span class="sxs-lookup"><span data-stu-id="793d8-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="793d8-106">Avec un bit de transport encodé dans qubit `carryIn` et deux bits opérande encodés dans `summand1` et `summand2` , calcule le XOR au niveau du bit de `carryIn` et `summand1` `summand2` dans le qubit `summand2` et le résultat est XOR au qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="793d8-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="793d8-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="793d8-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="793d8-108">Port : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="793d8-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="793d8-109">Qubit de transport.</span><span class="sxs-lookup"><span data-stu-id="793d8-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="793d8-110">summand1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="793d8-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="793d8-111">Premier opérande qubit.</span><span class="sxs-lookup"><span data-stu-id="793d8-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="793d8-112">summand2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="793d8-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="793d8-113">Le deuxième opérande qubit, est remplacé par le bit inférieur de la somme de `summand1` et `summand2` .</span><span class="sxs-lookup"><span data-stu-id="793d8-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="793d8-114">carryOut : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="793d8-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="793d8-115">Procédez à la qubit, sera XOR avec le bit le plus élevé de la somme.</span><span class="sxs-lookup"><span data-stu-id="793d8-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="793d8-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="793d8-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

