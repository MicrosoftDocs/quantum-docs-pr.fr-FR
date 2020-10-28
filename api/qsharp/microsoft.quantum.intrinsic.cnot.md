---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: Opération CNOTIN
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708081"
---
# <a name="cnot-operation"></a><span data-ttu-id="e8f39-102">Opération CNOTIN</span><span class="sxs-lookup"><span data-stu-id="e8f39-102">CNOT operation</span></span>

<span data-ttu-id="e8f39-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e8f39-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e8f39-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8f39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8f39-105">Applique la porte contrôlée-NOT (CNOTIN) à une paire de qubits.</span><span class="sxs-lookup"><span data-stu-id="e8f39-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="e8f39-106">\begin{align} \operatorname{CNOT} \mathrel{ : =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="e8f39-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="e8f39-107">où les lignes et les colonnes sont classées comme dans le guide des concepts Quantum.</span><span class="sxs-lookup"><span data-stu-id="e8f39-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e8f39-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="e8f39-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="e8f39-109">contrôle : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8f39-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8f39-110">Contrôle qubit pour la porte CNOTIN.</span><span class="sxs-lookup"><span data-stu-id="e8f39-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e8f39-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8f39-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8f39-112">Qubit cible de la porte CNOTIN.</span><span class="sxs-lookup"><span data-stu-id="e8f39-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8f39-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8f39-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e8f39-114">Notes</span><span class="sxs-lookup"><span data-stu-id="e8f39-114">Remarks</span></span>

<span data-ttu-id="e8f39-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="e8f39-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```