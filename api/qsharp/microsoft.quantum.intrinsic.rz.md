---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Opération RZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707107"
---
# <a name="rz-operation"></a><span data-ttu-id="012ea-102">Opération RZ</span><span class="sxs-lookup"><span data-stu-id="012ea-102">Rz operation</span></span>

<span data-ttu-id="012ea-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="012ea-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="012ea-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="012ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="012ea-105">Applique une rotation autour du $z $-AXIS par un angle donné.</span><span class="sxs-lookup"><span data-stu-id="012ea-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="012ea-106">\begin{align} R_z (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \Theta/2} & 0 \\ \\ 0 & e ^ {i \Theta/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="012ea-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="012ea-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="012ea-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="012ea-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="012ea-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="012ea-109">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="012ea-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="012ea-110">Angle sur lequel le qubit doit être pivoté.</span><span class="sxs-lookup"><span data-stu-id="012ea-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="012ea-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="012ea-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="012ea-112">Qubit auquel la porte doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="012ea-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="012ea-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="012ea-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="012ea-114">Notes</span><span class="sxs-lookup"><span data-stu-id="012ea-114">Remarks</span></span>

<span data-ttu-id="012ea-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="012ea-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```