---
uid: Microsoft.Quantum.Canon.CX
title: Fonctionnement de CX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4eaecf372f3054de4886b1e42c6b4ce386a22f73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207239"
---
# <a name="cx-operation"></a><span data-ttu-id="38676-102">Fonctionnement de CX</span><span class="sxs-lookup"><span data-stu-id="38676-102">CX operation</span></span>

<span data-ttu-id="38676-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="38676-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="38676-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38676-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38676-105">Applique la porte contrôlée X (CX) à une paire de qubits.</span><span class="sxs-lookup"><span data-stu-id="38676-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="38676-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $ où les lignes et les colonnes sont organisées comme dans le guide des concepts de Quantum.</span><span class="sxs-lookup"><span data-stu-id="38676-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="38676-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="38676-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="38676-108">contrôle : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="38676-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="38676-109">Contrôler qubit pour la porte CX.</span><span class="sxs-lookup"><span data-stu-id="38676-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="38676-110">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="38676-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="38676-111">Qubit cible de la porte CX.</span><span class="sxs-lookup"><span data-stu-id="38676-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38676-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38676-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="38676-113">Notes</span><span class="sxs-lookup"><span data-stu-id="38676-113">Remarks</span></span>

<span data-ttu-id="38676-114">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="38676-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="38676-115">et :</span><span class="sxs-lookup"><span data-stu-id="38676-115">and to:</span></span>

```qsharp
CNOT(control, target);
```