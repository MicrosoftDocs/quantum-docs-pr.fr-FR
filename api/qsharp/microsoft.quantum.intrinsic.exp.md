---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Opération exp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819010"
---
# <a name="exp-operation"></a><span data-ttu-id="2298b-102">Opération exp</span><span class="sxs-lookup"><span data-stu-id="2298b-102">Exp operation</span></span>

<span data-ttu-id="2298b-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2298b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2298b-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2298b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2298b-105">Applique l’exponentiel d’un opérateur qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="2298b-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="2298b-106">\begin{align} e ^ {i \Theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} où $P _i $ est le $i élément $ Th de `paulis` , et où $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="2298b-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2298b-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="2298b-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="2298b-108">Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="2298b-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="2298b-109">Tableau de valeurs Pauli à qubit unique indiquant les facteurs de produit tenseur sur chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="2298b-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="2298b-110">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2298b-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2298b-111">Angle à l’aide de l’opérateur Pauli qubit donné par lequel le registre cible doit pivoter.</span><span class="sxs-lookup"><span data-stu-id="2298b-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2298b-112">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2298b-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2298b-113">Inscrivez-vous pour appliquer la rotation donnée à.</span><span class="sxs-lookup"><span data-stu-id="2298b-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2298b-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2298b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

