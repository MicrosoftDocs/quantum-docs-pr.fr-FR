---
uid: Microsoft.Quantum.Intrinsic.M
title: Opération M
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707155"
---
# <a name="m-operation"></a>Opération M

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Effectue une mesure d’un seul qubit dans le Pauli $Z $.

Le résultat de la sortie est donné par la \begin{align} de distribution \Pr (\texttt{Zero} | \ket{\Psi}) = \braket{\Psi | 0} \braket{0 | \Psi}.
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>Entrée

### <a name="qubit--qubit"></a>qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit à mesurer.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

`Zero` Si le eigenvalue $ + $1 est observé et `One` si le eigenvalue $-$1 est observé.

## <a name="remarks"></a>Notes

Équivalent à :

```qsharp
Measure([PauliZ], [qubit]);
```