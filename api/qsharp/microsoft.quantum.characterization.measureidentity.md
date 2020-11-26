---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Opération MeasureIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216113"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="0704a-102">Opération MeasureIdentity</span><span class="sxs-lookup"><span data-stu-id="0704a-102">MeasureIdentity operation</span></span>

<span data-ttu-id="0704a-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="0704a-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="0704a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0704a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0704a-105">Mesure l’opérateur d’identité sur un registre de qubits.</span><span class="sxs-lookup"><span data-stu-id="0704a-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="0704a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0704a-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="0704a-107">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0704a-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0704a-108">Registre à mesurer.</span><span class="sxs-lookup"><span data-stu-id="0704a-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="0704a-109">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="0704a-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="0704a-110">Valeur de résultat `Zero` .</span><span class="sxs-lookup"><span data-stu-id="0704a-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0704a-111">Notes</span><span class="sxs-lookup"><span data-stu-id="0704a-111">Remarks</span></span>

<span data-ttu-id="0704a-112">Étant donné que $ \boldone $ contient uniquement le eigenvalue $1 $, et qu’il n’a pas de eigenvalue négatif, cette opération retourne toujours `Zero` , ce qui correspond au eigenvalue $ + 1 = (-1) ^ 0 $ et n’entraîne pas la réduction de l’état de `register` .</span><span class="sxs-lookup"><span data-stu-id="0704a-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="0704a-113">En soi, cette opération n’est pas utile, mais elle est utile dans le contexte de la tomographie de processus, car elle fournit des informations sur la conservation de trace d’un processus de Quantum.</span><span class="sxs-lookup"><span data-stu-id="0704a-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="0704a-114">En particulier, une machine cible avec une mesure de perte doit remplacer cette opération par une mesure réelle de $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="0704a-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>