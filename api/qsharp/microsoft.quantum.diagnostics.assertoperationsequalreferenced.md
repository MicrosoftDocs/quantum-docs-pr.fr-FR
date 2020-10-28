---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Opération AssertOperationsEqualReferenced
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702748"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="389eb-102">Opération AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="389eb-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="389eb-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="389eb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="389eb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="389eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="389eb-105">À partir de deux opérations, déclare qu’elles agissent de la même manière pour tous les États d’entrée.</span><span class="sxs-lookup"><span data-stu-id="389eb-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="389eb-106">Cette assertion est implémentée à l’aide de la isomorphism Choi – Jamiołkowski pour réduire l’assertion à l’une des affirmations d’état de qubit sur deux registres.</span><span class="sxs-lookup"><span data-stu-id="389eb-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="389eb-107">Par conséquent, cette opération n’a besoin que d’un seul appel à chaque opération en cours de test, mais nécessite deux fois plus de qubits à allouer.</span><span class="sxs-lookup"><span data-stu-id="389eb-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="389eb-108">Cette assertion peut être utilisée pour s’assurer, par exemple, qu’une version optimisée d’une opération agit de la même manière que son implémentation naïve, ou qu’une opération qui agit sur une plage d’entrées non quantiques accepte les cas connus.</span><span class="sxs-lookup"><span data-stu-id="389eb-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="389eb-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="389eb-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="389eb-110">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="389eb-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="389eb-111">Nombre de qubits à transmettre à chaque opération.</span><span class="sxs-lookup"><span data-stu-id="389eb-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="389eb-112">réel : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="389eb-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="389eb-113">Opération à tester.</span><span class="sxs-lookup"><span data-stu-id="389eb-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="389eb-114">ATTENDU : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="389eb-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="389eb-115">Opération définissant le comportement attendu pour l’opération testée.</span><span class="sxs-lookup"><span data-stu-id="389eb-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="389eb-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="389eb-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="389eb-117">Notes</span><span class="sxs-lookup"><span data-stu-id="389eb-117">Remarks</span></span>

<span data-ttu-id="389eb-118">Cette opération nécessite que l’opération modélisant le comportement attendu soit adjointable, afin que l’inverse puisse être effectué sur le registre cible seul.</span><span class="sxs-lookup"><span data-stu-id="389eb-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="389eb-119">Formellement, il est possible de spécifier une opération de transposer, qui assouplit cette exigence, mais l’opération de transposer n’est pas en général physiquement réalisable pour les opérations de Quantum arbitraires et n’est donc pas incluse ici comme une option.</span><span class="sxs-lookup"><span data-stu-id="389eb-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>