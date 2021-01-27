---
uid: Microsoft.Quantum.Canon.CY
title: Opération CY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 862f058e630ee6d9159e0fe514ca2dd1179ea9a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840735"
---
# <a name="cy-operation"></a><span data-ttu-id="8e0f8-102">Opération CY</span><span class="sxs-lookup"><span data-stu-id="8e0f8-102">CY operation</span></span>

<span data-ttu-id="8e0f8-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8e0f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8e0f8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e0f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e0f8-105">Applique la porte contrôlée-Y (CY) à une paire de qubits.</span><span class="sxs-lookup"><span data-stu-id="8e0f8-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="8e0f8-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & i & 0 \end{align}, $ $ où les lignes et les colonnes sont organisées comme dans le guide des concepts de Quantum.</span><span class="sxs-lookup"><span data-stu-id="8e0f8-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8e0f8-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="8e0f8-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="8e0f8-108">contrôle : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8e0f8-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8e0f8-109">Contrôle qubit pour la porte CY.</span><span class="sxs-lookup"><span data-stu-id="8e0f8-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8e0f8-110">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8e0f8-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8e0f8-111">Qubit cible de la porte CY.</span><span class="sxs-lookup"><span data-stu-id="8e0f8-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e0f8-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e0f8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8e0f8-113">Notes</span><span class="sxs-lookup"><span data-stu-id="8e0f8-113">Remarks</span></span>

<span data-ttu-id="8e0f8-114">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="8e0f8-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```