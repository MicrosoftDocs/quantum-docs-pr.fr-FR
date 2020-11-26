---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Opération RFrac
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: bd182ea50d747e07bb0f8051c5dbc128b7ff7674
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198637"
---
# <a name="rfrac-operation"></a><span data-ttu-id="46a51-102">Opération RFrac</span><span class="sxs-lookup"><span data-stu-id="46a51-102">RFrac operation</span></span>

<span data-ttu-id="46a51-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="46a51-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="46a51-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="46a51-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="46a51-105">Applique une rotation autour de l’axe de Pauli donné par un angle spécifié comme une fraction dyadic.</span><span class="sxs-lookup"><span data-stu-id="46a51-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="46a51-106">\begin{align} R_ {\mu} (n, k) \mathrel{ : =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align} où $ \mu \Dans \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="46a51-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="46a51-107">Cette opération utilise la Convention de signe **opposée** de @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="46a51-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="46a51-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="46a51-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="46a51-109">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="46a51-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="46a51-110">Opérateur Pauli à élever pour former la rotation.</span><span class="sxs-lookup"><span data-stu-id="46a51-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="46a51-111">Numérateur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46a51-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46a51-112">Numérateur dans la représentation dyadic de la fraction de l’angle par lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="46a51-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="46a51-113">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46a51-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46a51-114">Puissance de deux spécifiant le dénominateur de l’angle par lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="46a51-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="46a51-115">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="46a51-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="46a51-116">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="46a51-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46a51-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46a51-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="46a51-118">Notes</span><span class="sxs-lookup"><span data-stu-id="46a51-118">Remarks</span></span>

<span data-ttu-id="46a51-119">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="46a51-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```