---
uid: Microsoft.Quantum.Intrinsic.R1
title: Opération R1
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707142"
---
# <a name="r1-operation"></a>Opération R1

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Applique une rotation autour de l’État $ \ket {1} $ d’un angle donné.

\begin{align} R_1 (\Theta) \mathrel{ : =} \operatorname{Diag} (1, e ^ {i\theta}).
\end{align}

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
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
R(PauliI, -theta, qubit);
```