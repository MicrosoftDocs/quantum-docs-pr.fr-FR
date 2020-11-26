---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Opération RX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 49638c00967ff2f47dad41acfed05868d65a24a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198586"
---
# <a name="rx-operation"></a><span data-ttu-id="92df6-102">Opération RX</span><span class="sxs-lookup"><span data-stu-id="92df6-102">Rx operation</span></span>

<span data-ttu-id="92df6-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="92df6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="92df6-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="92df6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="92df6-105">Applique une rotation autour du $x $-AXIS par un angle donné.</span><span class="sxs-lookup"><span data-stu-id="92df6-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="92df6-106">\begin{align} R_x (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\Theta} {2} &-i\sin \frac{\Theta} {2} \\ \\ -i\sin \frac{\Theta} {2} & \cos {2} \frac{\Theta} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="92df6-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="92df6-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="92df6-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="92df6-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="92df6-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="92df6-109">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="92df6-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="92df6-110">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="92df6-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="92df6-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="92df6-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="92df6-112">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="92df6-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="92df6-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92df6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="92df6-114">Notes</span><span class="sxs-lookup"><span data-stu-id="92df6-114">Remarks</span></span>

<span data-ttu-id="92df6-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="92df6-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```