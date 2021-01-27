---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Opération PrepareEntangledState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854362"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="e7b86-102">Opération PrepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="e7b86-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="e7b86-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e7b86-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e7b86-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7b86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7b86-105">La paire d’une paire passe en deux registres qubit.</span><span class="sxs-lookup"><span data-stu-id="e7b86-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="e7b86-106">Autrement dit, à partir de deux registres, prépare l’état maximal pris en compte $ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ entre chaque paire de qubits sur les registres respectifs, en supposant que chaque registre commence dans l’État $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="e7b86-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e7b86-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e7b86-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="e7b86-108">gauche : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e7b86-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e7b86-109">Un tableau qubit dans l’État $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="e7b86-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="e7b86-110">Right : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e7b86-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e7b86-111">Un tableau qubit dans l’État $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="e7b86-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7b86-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7b86-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

