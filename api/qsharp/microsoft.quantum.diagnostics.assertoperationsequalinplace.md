---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Opération AssertOperationsEqualInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 7c330ebdc156e60713a734d39a3600ee1326563c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853483"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="395e2-102">Opération AssertOperationsEqualInPlace</span><span class="sxs-lookup"><span data-stu-id="395e2-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="395e2-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="395e2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="395e2-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="395e2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="395e2-105">À partir de deux opérations, déclare qu’elles agissent de la même manière pour tous les États d’entrée.</span><span class="sxs-lookup"><span data-stu-id="395e2-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="395e2-106">Cette assertion est implémentée en vérifiant l’action des opérations sur tous les États de la forme $V _0 \otimes... \otimes V_ {n-1} $, où $V _k $ est l’un des États $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ et $ \ket{i} $ (+ 1 eigenstate de l’opérateur Y Pauli).</span><span class="sxs-lookup"><span data-stu-id="395e2-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="395e2-107">Cette assertion utilise $n $ qubits et nécessite plusieurs appels des opérations comparées.</span><span class="sxs-lookup"><span data-stu-id="395e2-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="395e2-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="395e2-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="395e2-109">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="395e2-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="395e2-110">Nombre de qubits $n $ que les opérations `givenU` et `expectedU` utilisent.</span><span class="sxs-lookup"><span data-stu-id="395e2-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="395e2-111">donné : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unité](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="395e2-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="395e2-112">Opération sur $n $ qubits à vérifier.</span><span class="sxs-lookup"><span data-stu-id="395e2-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="395e2-113">expected : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="395e2-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="395e2-114">Opération de référence sur $n $ qubits `givenU` à comparer.</span><span class="sxs-lookup"><span data-stu-id="395e2-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="395e2-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="395e2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="395e2-116">Références</span><span class="sxs-lookup"><span data-stu-id="395e2-116">References</span></span>

<span data-ttu-id="395e2-117">La base des États $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ et $ \ket{i} $ est la base de Chuang-Nielsen, décrite dans [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="395e2-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="395e2-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="395e2-118">See Also</span></span>

- [<span data-ttu-id="395e2-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="395e2-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)