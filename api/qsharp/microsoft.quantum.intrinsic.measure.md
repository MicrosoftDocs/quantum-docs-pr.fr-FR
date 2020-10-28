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
# <a name="measure-operation"></a><span data-ttu-id="e4cf8-102">Opération de mesure</span><span class="sxs-lookup"><span data-stu-id="e4cf8-102">Measure operation</span></span>

<span data-ttu-id="e4cf8-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e4cf8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e4cf8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4cf8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4cf8-105">Effectue une mesure conjointe d’un ou plusieurs qubits dans les bases Pauli spécifiées.</span><span class="sxs-lookup"><span data-stu-id="e4cf8-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="e4cf8-106">Le résultat de la sortie est donné par la distribution : \begin{align} \Pr (\texttt{Zero} | \ket{\Psi}) = \frac12 \braket{\Psi \mid | \left (\boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \Psi}, \end{align} où $P _i $ est le $i élément $ Th de `bases` , et où $N = \texttt{length} (\texttt{bases}) $.</span><span class="sxs-lookup"><span data-stu-id="e4cf8-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="e4cf8-107">Autrement dit, la mesure retourne un `Result` $d $ de telle sorte que le eigenvalue de l’effet de mesure observé est $ (-1) ^ d $.</span><span class="sxs-lookup"><span data-stu-id="e4cf8-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="e4cf8-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="e4cf8-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="e4cf8-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e4cf8-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="e4cf8-110">Tableau de valeurs Pauli à qubit unique indiquant les facteurs de produit tenseur sur chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="e4cf8-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e4cf8-111">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4cf8-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e4cf8-112">Registre de qubits à mesurer.</span><span class="sxs-lookup"><span data-stu-id="e4cf8-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e4cf8-113">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="e4cf8-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="e4cf8-114">`Zero` Si le eigenvalue $ + $1 est observé et `One` si le eigenvalue $-$1 est observé.</span><span class="sxs-lookup"><span data-stu-id="e4cf8-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4cf8-115">Notes</span><span class="sxs-lookup"><span data-stu-id="e4cf8-115">Remarks</span></span>

<span data-ttu-id="e4cf8-116">Si le tableau de base et le tableau qubit ont des longueurs différentes, l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="e4cf8-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>