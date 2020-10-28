---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Opération exp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702133"
---
# <a name="exp-operation"></a><span data-ttu-id="145c5-102">Opération exp</span><span class="sxs-lookup"><span data-stu-id="145c5-102">Exp operation</span></span>

<span data-ttu-id="145c5-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="145c5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="145c5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="145c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="145c5-105">Applique l’exponentiel d’un opérateur qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="145c5-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="145c5-106">\begin{align} e ^ {i \Theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align} où $P _i $ est le $i élément $ Th de `paulis` , et où $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="145c5-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="145c5-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="145c5-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="145c5-108">Paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="145c5-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="145c5-109">Tableau de valeurs Pauli à qubit unique indiquant les facteurs de produit tenseur sur chaque qubit.</span><span class="sxs-lookup"><span data-stu-id="145c5-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="145c5-110">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="145c5-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="145c5-111">Angle à l’aide de l’opérateur Pauli qubit donné par lequel le registre cible doit pivoter.</span><span class="sxs-lookup"><span data-stu-id="145c5-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="145c5-112">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="145c5-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="145c5-113">Inscrivez-vous pour appliquer la rotation donnée à.</span><span class="sxs-lookup"><span data-stu-id="145c5-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="145c5-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="145c5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

