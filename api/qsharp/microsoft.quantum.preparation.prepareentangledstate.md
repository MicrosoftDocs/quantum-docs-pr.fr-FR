---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Opération PrepareEntangledState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210469"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="32a68-102">Opération PrepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="32a68-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="32a68-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="32a68-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="32a68-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32a68-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32a68-105">La paire d’une paire passe en deux registres qubit.</span><span class="sxs-lookup"><span data-stu-id="32a68-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="32a68-106">Autrement dit, à partir de deux registres, prépare l’état maximal pris en compte $ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ entre chaque paire de qubits sur les registres respectifs, en supposant que chaque registre commence dans l’État $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="32a68-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="32a68-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="32a68-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="32a68-108">gauche : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="32a68-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="32a68-109">Un tableau qubit dans l’État $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="32a68-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="32a68-110">Right : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="32a68-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="32a68-111">Un tableau qubit dans l’État $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="32a68-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="32a68-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32a68-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

