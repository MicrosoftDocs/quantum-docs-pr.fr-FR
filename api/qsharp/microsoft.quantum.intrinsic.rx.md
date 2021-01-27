---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Opération RX
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: b6224952ea5eabfc7177ead557378fb07b9e597f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849299"
---
# <a name="rx-operation"></a><span data-ttu-id="f7781-102">Opération RX</span><span class="sxs-lookup"><span data-stu-id="f7781-102">Rx operation</span></span>

<span data-ttu-id="f7781-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f7781-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f7781-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f7781-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f7781-105">Applique une rotation autour du $x $-AXIS par un angle donné.</span><span class="sxs-lookup"><span data-stu-id="f7781-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="f7781-106">\begin{align} R_x (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\Theta} {2} &-i\sin \frac{\Theta} {2} \\ \\ -i\sin \frac{\Theta} {2} & \cos {2} \frac{\Theta} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="f7781-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="f7781-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f7781-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f7781-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="f7781-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="f7781-109">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f7781-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f7781-110">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="f7781-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="f7781-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7781-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7781-112">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="f7781-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7781-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7781-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f7781-114">Notes</span><span class="sxs-lookup"><span data-stu-id="f7781-114">Remarks</span></span>

<span data-ttu-id="f7781-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="f7781-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```