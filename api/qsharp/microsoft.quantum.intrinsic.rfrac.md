---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Opération RFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708441"
---
# <a name="rfrac-operation"></a><span data-ttu-id="5dc70-102">Opération RFrac</span><span class="sxs-lookup"><span data-stu-id="5dc70-102">RFrac operation</span></span>

<span data-ttu-id="5dc70-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5dc70-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5dc70-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5dc70-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5dc70-105">Applique une rotation autour de l’axe de Pauli donné par un angle spécifié comme une fraction dyadic.</span><span class="sxs-lookup"><span data-stu-id="5dc70-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="5dc70-106">\begin{align} R_ {\mu} (n, k) \mathrel{ : =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align} où $ \mu \Dans \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="5dc70-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="5dc70-107">Cette opération utilise la Convention de signe **opposée** de @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="5dc70-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5dc70-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="5dc70-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="5dc70-109">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="5dc70-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="5dc70-110">Opérateur Pauli à élever pour former la rotation.</span><span class="sxs-lookup"><span data-stu-id="5dc70-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="5dc70-111">Numérateur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5dc70-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5dc70-112">Numérateur dans la représentation dyadic de la fraction de l’angle par lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="5dc70-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="5dc70-113">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5dc70-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5dc70-114">Puissance de deux spécifiant le dénominateur de l’angle par lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="5dc70-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="5dc70-115">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5dc70-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5dc70-116">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="5dc70-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5dc70-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5dc70-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5dc70-118">Notes</span><span class="sxs-lookup"><span data-stu-id="5dc70-118">Remarks</span></span>

<span data-ttu-id="5dc70-119">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="5dc70-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```