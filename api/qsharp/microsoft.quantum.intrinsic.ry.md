---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Opération ry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: b50225b67701c6b17475445d5ed54400240e0b69
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818280"
---
# <a name="ry-operation"></a><span data-ttu-id="4409c-102">Opération ry</span><span class="sxs-lookup"><span data-stu-id="4409c-102">Ry operation</span></span>

<span data-ttu-id="4409c-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4409c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4409c-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4409c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4409c-105">Applique une rotation autour du $y $-AXIS par un angle donné.</span><span class="sxs-lookup"><span data-stu-id="4409c-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="4409c-106">\begin{align} R_y (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\Theta} {2} &-\sin \frac{\Theta} \sin {2} \\ \\ \frac{\Theta} {2} & \cos \frac{\Theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="4409c-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="4409c-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="4409c-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4409c-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="4409c-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="4409c-109">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4409c-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4409c-110">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="4409c-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="4409c-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4409c-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4409c-112">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="4409c-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4409c-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4409c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4409c-114">Notes</span><span class="sxs-lookup"><span data-stu-id="4409c-114">Remarks</span></span>

<span data-ttu-id="4409c-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="4409c-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```