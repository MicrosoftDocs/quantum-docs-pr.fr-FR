---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Opération de mesure
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818767"
---
# <a name="measure-operation"></a><span data-ttu-id="314f3-102">Opération de mesure</span><span class="sxs-lookup"><span data-stu-id="314f3-102">Measure operation</span></span>

<span data-ttu-id="314f3-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="314f3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="314f3-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="314f3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="314f3-105">Effectue une mesure conjointe d’un ou plusieurs qubits dans les bases Pauli spécifiées.</span><span class="sxs-lookup"><span data-stu-id="314f3-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="314f3-106">Le résultat de la sortie est donné par la distribution : \begin{align} \Pr (\texttt{Zero} | \ket{\Psi}) = \frac12 \braket{\Psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \Psi}, \end{align} où $P _i $ est le $i élément $ Th de `bases` , et où $N = \texttt{length} (\texttt{bases}) $.</span><span class="sxs-lookup"><span data-stu-id="314f3-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="314f3-107">Autrement dit, la mesure retourne un `Result` $d $ de telle sorte que le eigenvalue de l’effet de mesure observé est $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="314f3-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="314f3-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="314f3-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="314f3-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="314f3-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="314f3-110">Tableau de valeurs Pauli à qubit unique indiquant les facteurs de produit tenseur sur chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="314f3-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="314f3-111">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="314f3-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="314f3-112">Registre de qubits à mesurer.</span><span class="sxs-lookup"><span data-stu-id="314f3-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="314f3-113">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="314f3-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="314f3-114">`Zero` Si le eigenvalue $ + $1 est observé et `One` si le eigenvalue $-$1 est observé.</span><span class="sxs-lookup"><span data-stu-id="314f3-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="314f3-115">Notes</span><span class="sxs-lookup"><span data-stu-id="314f3-115">Remarks</span></span>

<span data-ttu-id="314f3-116">Si le tableau de base et le tableau qubit ont des longueurs différentes, l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="314f3-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>