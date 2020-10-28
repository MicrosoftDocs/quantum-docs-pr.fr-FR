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
# <a name="rz-operation"></a>Opération RZ

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Applique une rotation autour du $z $-AXIS par un angle donné.

\begin{align} R_z (\Theta) \mathrel{ : =} e ^ {-i \Theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \Theta/2} & 0 \\ \\ 0 & e ^ {i \Theta/2} \end{bmatrix}.
\end{align}

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
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
R(PauliZ, theta, qubit);
```