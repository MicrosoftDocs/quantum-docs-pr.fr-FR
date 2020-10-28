---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Opération de mesure
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 56ddfbe5e63692e477ad75bde6b1b16269ed20c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702103"
---
# <a name="measure-operation"></a>Opération de mesure

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Effectue une mesure conjointe d’un ou plusieurs qubits dans les bases Pauli spécifiées.

Le résultat de la sortie est donné par la distribution : \begin{align} \Pr (\texttt{Zero} | \ket{\Psi}) = \frac12 \braket{\Psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \Psi}, \end{align} où $P _i $ est le $i élément $ Th de `bases` , et où $N = \texttt{length} (\texttt{bases}) $.
Autrement dit, la mesure retourne un `Result` $d $ de telle sorte que le eigenvalue de l’effet de mesure observé est $ (-1) ^ d $.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Entrée

### <a name="bases--pauli"></a>bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tableau de valeurs Pauli à qubit unique indiquant les facteurs de produit tenseur sur chaque qubit.


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de qubits à mesurer.



## <a name="output--__invalidresult__"></a>Sortie : __non <Result> valide__

`Zero` Si le eigenvalue $ + $1 est observé et `One` si le eigenvalue $-$1 est observé.

## <a name="remarks"></a>Notes

Si le tableau de base et le tableau qubit ont des longueurs différentes, l’opération échoue.