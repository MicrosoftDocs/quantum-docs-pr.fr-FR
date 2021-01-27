---
uid: Microsoft.Quantum.Canon.CX
title: Fonctionnement de CX
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840752"
---
# <a name="cx-operation"></a><span data-ttu-id="aa25e-102">Fonctionnement de CX</span><span class="sxs-lookup"><span data-stu-id="aa25e-102">CX operation</span></span>

<span data-ttu-id="aa25e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa25e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa25e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa25e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa25e-105">Applique la porte contrôlée X (CX) à une paire de qubits.</span><span class="sxs-lookup"><span data-stu-id="aa25e-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="aa25e-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $ où les lignes et les colonnes sont organisées comme dans le guide des concepts de Quantum.</span><span class="sxs-lookup"><span data-stu-id="aa25e-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="aa25e-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="aa25e-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="aa25e-108">contrôle : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa25e-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa25e-109">Contrôler qubit pour la porte CX.</span><span class="sxs-lookup"><span data-stu-id="aa25e-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="aa25e-110">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa25e-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa25e-111">Qubit cible de la porte CX.</span><span class="sxs-lookup"><span data-stu-id="aa25e-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa25e-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa25e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa25e-113">Notes</span><span class="sxs-lookup"><span data-stu-id="aa25e-113">Remarks</span></span>

<span data-ttu-id="aa25e-114">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="aa25e-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="aa25e-115">et :</span><span class="sxs-lookup"><span data-stu-id="aa25e-115">and to:</span></span>

```qsharp
CNOT(control, target);
```