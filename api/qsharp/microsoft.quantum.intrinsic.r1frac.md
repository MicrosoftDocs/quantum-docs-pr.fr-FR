---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: Opération R1Frac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707131"
---
# <a name="r1frac-operation"></a><span data-ttu-id="cd231-102">Opération R1Frac</span><span class="sxs-lookup"><span data-stu-id="cd231-102">R1Frac operation</span></span>

<span data-ttu-id="cd231-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cd231-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cd231-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd231-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd231-105">Applique une rotation autour de l’État $ \ket {1} $ par un angle spécifié comme une fraction dyadic.</span><span class="sxs-lookup"><span data-stu-id="cd231-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="cd231-106">\begin{align} R_1 (n, k) \mathrel{ : =} \operatorname{Diag} (1, e ^ {i \pi k/2 ^ n}).</span><span class="sxs-lookup"><span data-stu-id="cd231-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="cd231-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="cd231-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="cd231-108">Cette opération utilise la Convention de signe **opposée** de @"microsoft.quantum.intrinsic.r" et n’inclut pas le facteur de $1/2 $ inclus par @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="cd231-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="cd231-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="cd231-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="cd231-110">Numérateur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd231-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd231-111">Numérateur dans la représentation dyadic de la fraction de l’angle par lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="cd231-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="cd231-112">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd231-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd231-113">Puissance de deux spécifiant le dénominateur de l’angle par lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="cd231-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="cd231-114">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cd231-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cd231-115">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="cd231-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd231-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd231-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cd231-117">Notes</span><span class="sxs-lookup"><span data-stu-id="cd231-117">Remarks</span></span>

<span data-ttu-id="cd231-118">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="cd231-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```