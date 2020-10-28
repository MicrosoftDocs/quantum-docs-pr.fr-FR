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
# <a name="ry-operation"></a>Opération ry

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Applique une rotation autour du $y $-AXIS par un angle donné.

\begin{align} R_y (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\Theta} {2} &-\sin \frac{\Theta} \sin {2} \\ \\ \frac{\Theta} {2} & \cos \frac{\Theta} {2} \end{bmatrix}.  
\end{align}

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a>Entrée

### <a name="theta--double"></a>thêta : [double](xref:microsoft.quantum.lang-ref.double)

Angle sur lequel le qubit doit être pivoté.


### <a name="qubit--qubit"></a>qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auquel la porte doit être appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Équivalent à :

```qsharp
R(PauliY, theta, qubit);
```