---
uid: Microsoft.Quantum.Canon.CZ
title: CZ, opération
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704270"
---
# <a name="cz-operation"></a><span data-ttu-id="6ec0b-102">CZ, opération</span><span class="sxs-lookup"><span data-stu-id="6ec0b-102">CZ operation</span></span>

<span data-ttu-id="6ec0b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ec0b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ec0b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ec0b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ec0b-105">Applique la porte contrôlée-Z (CZ) à une paire de qubits.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="6ec0b-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $ où les lignes et les colonnes sont organisées comme dans le guide des concepts de Quantum.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6ec0b-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="6ec0b-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="6ec0b-108">contrôle : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6ec0b-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6ec0b-109">Contrôle qubit pour la porte de la porte.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6ec0b-110">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6ec0b-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6ec0b-111">Qubit cible pour la porte CZ.</span><span class="sxs-lookup"><span data-stu-id="6ec0b-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ec0b-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ec0b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6ec0b-113">Notes</span><span class="sxs-lookup"><span data-stu-id="6ec0b-113">Remarks</span></span>

<span data-ttu-id="6ec0b-114">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="6ec0b-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```