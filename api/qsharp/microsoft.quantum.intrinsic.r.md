---
uid: Microsoft.Quantum.Intrinsic.R
title: Opération R
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707150"
---
# <a name="r-operation"></a><span data-ttu-id="23308-102">Opération R</span><span class="sxs-lookup"><span data-stu-id="23308-102">R operation</span></span>

<span data-ttu-id="23308-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="23308-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="23308-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23308-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23308-105">Applique une rotation autour de l’axe Pauli donné.</span><span class="sxs-lookup"><span data-stu-id="23308-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="23308-106">\begin{align} R_ {\mu} (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_ {\mu}/2}, \end{align} où $ \mu \Dans \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="23308-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="23308-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="23308-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="23308-108">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="23308-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="23308-109">Opérateur Pauli ($ \mu $) à élever pour former la rotation.</span><span class="sxs-lookup"><span data-stu-id="23308-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="23308-110">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="23308-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="23308-111">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="23308-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="23308-112">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="23308-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="23308-113">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="23308-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="23308-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23308-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="23308-115">Notes</span><span class="sxs-lookup"><span data-stu-id="23308-115">Remarks</span></span>

<span data-ttu-id="23308-116">Quand elle est appelée avec `pauli = PauliI` , cette opération applique une *phase globale* .</span><span class="sxs-lookup"><span data-stu-id="23308-116">When called with `pauli = PauliI`, this operation applies a *global phase* .</span></span> <span data-ttu-id="23308-117">Cette phase peut être significative lorsqu’elle est utilisée avec `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="23308-117">This phase can be significant when used with the `Controlled` functor.</span></span>