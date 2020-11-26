---
uid: Microsoft.Quantum.Intrinsic.R
title: Opération R
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199027"
---
# <a name="r-operation"></a><span data-ttu-id="cf064-102">Opération R</span><span class="sxs-lookup"><span data-stu-id="cf064-102">R operation</span></span>

<span data-ttu-id="cf064-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cf064-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cf064-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cf064-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cf064-105">Applique une rotation autour de l’axe Pauli donné.</span><span class="sxs-lookup"><span data-stu-id="cf064-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="cf064-106">\begin{align} R_ {\mu} (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_ {\mu}/2}, \end{align} où $ \mu \Dans \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="cf064-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cf064-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="cf064-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="cf064-108">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="cf064-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="cf064-109">Opérateur Pauli ($ \mu $) à élever pour former la rotation.</span><span class="sxs-lookup"><span data-stu-id="cf064-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="cf064-110">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cf064-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cf064-111">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="cf064-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="cf064-112">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cf064-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cf064-113">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="cf064-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf064-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf064-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cf064-115">Notes</span><span class="sxs-lookup"><span data-stu-id="cf064-115">Remarks</span></span>

<span data-ttu-id="cf064-116">Quand elle est appelée avec `pauli = PauliI` , cette opération applique une *phase globale*.</span><span class="sxs-lookup"><span data-stu-id="cf064-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="cf064-117">Cette phase peut être significative lorsqu’elle est utilisée avec `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="cf064-117">This phase can be significant when used with the `Controlled` functor.</span></span>