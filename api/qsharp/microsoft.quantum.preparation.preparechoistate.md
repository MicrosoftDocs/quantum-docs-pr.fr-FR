---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Opération PrepareChoiState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210571"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="76e6d-102">Opération PrepareChoiState</span><span class="sxs-lookup"><span data-stu-id="76e6d-102">PrepareChoiState operation</span></span>

<span data-ttu-id="76e6d-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="76e6d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="76e6d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76e6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76e6d-105">Prépare l’État Choi – Jamiołkowski pour une opération donnée sur des registres de référence et cibles donnés.</span><span class="sxs-lookup"><span data-stu-id="76e6d-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="76e6d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="76e6d-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="76e6d-107">OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76e6d-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="76e6d-108">L’opération $ \Lambda $ dont l’État Choi – Jamiołkowski $J (\Lambda)/2 ^ N $ doit être préparée, où $N $ est le nombre de qubits sur lequel `op` agit.</span><span class="sxs-lookup"><span data-stu-id="76e6d-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="76e6d-109">Référence : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="76e6d-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="76e6d-110">Un registre de qubits à partir de l’État $ \ket{00\cdots 0} $ à utiliser comme référence pour l’action de `op` .</span><span class="sxs-lookup"><span data-stu-id="76e6d-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="76e6d-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="76e6d-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="76e6d-112">Un registre de qubits initialement dans l’État $ \ket{00\cdots 0} $ sur lequel `op` doit être appliqué.</span><span class="sxs-lookup"><span data-stu-id="76e6d-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76e6d-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76e6d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="76e6d-114">Notes</span><span class="sxs-lookup"><span data-stu-id="76e6d-114">Remarks</span></span>

<span data-ttu-id="76e6d-115">L’État Choi – Jamiłkowski $J (\Lambda) $ d’un processus Quantum est défini en tant que $ $ \begin{align} J (\Lambda) \mathrel{ : =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ où $ | X\rangle \! \rangle $ est la *vectorisation* d’une matrice $X $ dans la Convention d’empilement de colonnes.</span><span class="sxs-lookup"><span data-stu-id="76e6d-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="76e6d-116">L’apprentissage d’une description classique de cet État fournit des informations complètes sur l’effet de $ \Lambda $ agissant sur des États d’entrée arbitraires et constitue la base de la *tomographie de processus quantique*.</span><span class="sxs-lookup"><span data-stu-id="76e6d-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="76e6d-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76e6d-117">See Also</span></span>

- [<span data-ttu-id="76e6d-118">Microsoft. Quantum. PREPARATION. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="76e6d-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="76e6d-119">Microsoft. Quantum. PREPARATION. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="76e6d-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="76e6d-120">Microsoft. Quantum. PREPARATION. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="76e6d-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)