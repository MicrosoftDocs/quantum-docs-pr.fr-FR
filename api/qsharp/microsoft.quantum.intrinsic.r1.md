---
uid: Microsoft.Quantum.Intrinsic.R1
title: Opération R1
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: a98c2cc0b309a239650afd2910cc74dffa9f899a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198807"
---
# <a name="r1-operation"></a><span data-ttu-id="7ed41-102">Opération R1</span><span class="sxs-lookup"><span data-stu-id="7ed41-102">R1 operation</span></span>

<span data-ttu-id="7ed41-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7ed41-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7ed41-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7ed41-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7ed41-105">Applique une rotation autour de l’État $ \ket {1} $ d’un angle donné.</span><span class="sxs-lookup"><span data-stu-id="7ed41-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="7ed41-106">\begin{align} R_1 (\Theta) \mathrel{ : =} \operatorname{Diag} (1, e ^ {i\theta}).</span><span class="sxs-lookup"><span data-stu-id="7ed41-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="7ed41-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="7ed41-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7ed41-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="7ed41-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="7ed41-109">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ed41-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ed41-110">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="7ed41-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="7ed41-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7ed41-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7ed41-112">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="7ed41-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ed41-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ed41-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7ed41-114">Notes</span><span class="sxs-lookup"><span data-stu-id="7ed41-114">Remarks</span></span>

<span data-ttu-id="7ed41-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="7ed41-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```