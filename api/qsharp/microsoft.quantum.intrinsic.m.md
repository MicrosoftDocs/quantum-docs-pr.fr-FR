---
uid: Microsoft.Quantum.Intrinsic.M
title: Opération M
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818870"
---
# <a name="m-operation"></a>Opération M

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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