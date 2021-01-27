---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Opération ApplyFixedPointAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847231"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="10263-102">Opération ApplyFixedPointAmplification</span><span class="sxs-lookup"><span data-stu-id="10263-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="10263-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="10263-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="10263-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10263-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10263-105">Algorithme d’amplification d’amplitude Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="10263-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="10263-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="10263-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="10263-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="10263-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="10263-108">Oracle unitaire qui prépare l’état de démarrage.</span><span class="sxs-lookup"><span data-stu-id="10263-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="10263-109">startQubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="10263-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="10263-110">Registre qubit</span><span class="sxs-lookup"><span data-stu-id="10263-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="10263-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10263-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="10263-112">Notes</span><span class="sxs-lookup"><span data-stu-id="10263-112">Remarks</span></span>

<span data-ttu-id="10263-113">StartQubits doit être dans l’État $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="10263-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="10263-114">Cette opération effectue une itération sur un certain nombre de requêtes dans les puissances de $2 $ jusqu’à ce qu’un nombre maximal de requêtes soit atteint ou que l’État cible soit trouvé.</span><span class="sxs-lookup"><span data-stu-id="10263-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>