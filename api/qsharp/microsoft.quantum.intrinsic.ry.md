---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Opération ry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706534"
---
# <a name="ry-operation"></a><span data-ttu-id="5ec12-102">Opération ry</span><span class="sxs-lookup"><span data-stu-id="5ec12-102">Ry operation</span></span>

<span data-ttu-id="5ec12-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5ec12-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5ec12-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ec12-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ec12-105">Applique une rotation autour du $y $-AXIS par un angle donné.</span><span class="sxs-lookup"><span data-stu-id="5ec12-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="5ec12-106">\begin{align} R_y (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\Theta} {2} &-\sin \frac{\Theta} \sin {2} \\ \\ \frac{\Theta} {2} & \cos \frac{\Theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="5ec12-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="5ec12-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5ec12-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5ec12-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="5ec12-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="5ec12-109">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5ec12-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5ec12-110">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="5ec12-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="5ec12-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5ec12-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5ec12-112">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="5ec12-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ec12-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ec12-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5ec12-114">Notes</span><span class="sxs-lookup"><span data-stu-id="5ec12-114">Remarks</span></span>

<span data-ttu-id="5ec12-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="5ec12-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```