---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Opération AssertOperationsEqualReferenced
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853461"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="b4da9-102">Opération AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="b4da9-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="b4da9-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b4da9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b4da9-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b4da9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b4da9-105">À partir de deux opérations, déclare qu’elles agissent de la même manière pour tous les États d’entrée.</span><span class="sxs-lookup"><span data-stu-id="b4da9-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="b4da9-106">Cette assertion est implémentée à l’aide de la isomorphism Choi – Jamiołkowski pour réduire l’assertion à l’une des affirmations d’état de qubit sur deux registres.</span><span class="sxs-lookup"><span data-stu-id="b4da9-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="b4da9-107">Par conséquent, cette opération n’a besoin que d’un seul appel à chaque opération en cours de test, mais nécessite deux fois plus de qubits à allouer.</span><span class="sxs-lookup"><span data-stu-id="b4da9-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="b4da9-108">Cette assertion peut être utilisée pour s’assurer, par exemple, qu’une version optimisée d’une opération agit de la même manière que son implémentation naïve, ou qu’une opération qui agit sur une plage d’entrées non quantiques accepte les cas connus.</span><span class="sxs-lookup"><span data-stu-id="b4da9-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="b4da9-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="b4da9-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b4da9-110">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4da9-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4da9-111">Nombre de qubits à transmettre à chaque opération.</span><span class="sxs-lookup"><span data-stu-id="b4da9-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="b4da9-112">réel : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4da9-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b4da9-113">Opération à tester.</span><span class="sxs-lookup"><span data-stu-id="b4da9-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="b4da9-114">ATTENDU : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="b4da9-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b4da9-115">Opération définissant le comportement attendu pour l’opération testée.</span><span class="sxs-lookup"><span data-stu-id="b4da9-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4da9-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4da9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b4da9-117">Notes</span><span class="sxs-lookup"><span data-stu-id="b4da9-117">Remarks</span></span>

<span data-ttu-id="b4da9-118">Cette opération nécessite que l’opération modélisant le comportement attendu soit adjointable, afin que l’inverse puisse être effectué sur le registre cible seul.</span><span class="sxs-lookup"><span data-stu-id="b4da9-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="b4da9-119">Formellement, il est possible de spécifier une opération de transposer, qui assouplit cette exigence, mais l’opération de transposer n’est pas en général physiquement réalisable pour les opérations de Quantum arbitraires et n’est donc pas incluse ici comme une option.</span><span class="sxs-lookup"><span data-stu-id="b4da9-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>