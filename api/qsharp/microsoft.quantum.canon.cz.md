---
uid: Microsoft.Quantum.Canon.CZ
title: CZ, opération
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840703"
---
# <a name="cz-operation"></a><span data-ttu-id="18487-102">CZ, opération</span><span class="sxs-lookup"><span data-stu-id="18487-102">CZ operation</span></span>

<span data-ttu-id="18487-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="18487-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="18487-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18487-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18487-105">Applique la porte contrôlée-Z (CZ) à une paire de qubits.</span><span class="sxs-lookup"><span data-stu-id="18487-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="18487-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $ où les lignes et les colonnes sont organisées comme dans le guide des concepts de Quantum.</span><span class="sxs-lookup"><span data-stu-id="18487-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="18487-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="18487-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="18487-108">contrôle : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="18487-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="18487-109">Contrôle qubit pour la porte de la porte.</span><span class="sxs-lookup"><span data-stu-id="18487-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="18487-110">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="18487-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="18487-111">Qubit cible pour la porte CZ.</span><span class="sxs-lookup"><span data-stu-id="18487-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="18487-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18487-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="18487-113">Notes</span><span class="sxs-lookup"><span data-stu-id="18487-113">Remarks</span></span>

<span data-ttu-id="18487-114">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="18487-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```