---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Opération RZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: d637abf3562eb60705da517467939dc588229c39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198620"
---
# <a name="rz-operation"></a><span data-ttu-id="a183e-102">Opération RZ</span><span class="sxs-lookup"><span data-stu-id="a183e-102">Rz operation</span></span>

<span data-ttu-id="a183e-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a183e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a183e-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a183e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a183e-105">Applique une rotation autour du $z $-AXIS par un angle donné.</span><span class="sxs-lookup"><span data-stu-id="a183e-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="a183e-106">\begin{align} R_z (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \Theta/2} & 0 \\ \\ 0 & e ^ {i \Theta/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="a183e-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="a183e-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a183e-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a183e-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="a183e-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="a183e-109">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a183e-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a183e-110">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="a183e-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="a183e-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a183e-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a183e-112">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="a183e-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a183e-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a183e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a183e-114">Notes</span><span class="sxs-lookup"><span data-stu-id="a183e-114">Remarks</span></span>

<span data-ttu-id="a183e-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="a183e-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```