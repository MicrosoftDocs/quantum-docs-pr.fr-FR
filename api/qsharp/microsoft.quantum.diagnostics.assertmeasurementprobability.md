---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Opération AssertMeasurementProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830820"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="22563-102">Opération AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="22563-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="22563-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="22563-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="22563-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="22563-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="22563-105">Les assertions qui mesurent le qubits donné dans la base Pauli donnée auront le résultat donné avec la probabilité donnée, dans une certaine tolérance.</span><span class="sxs-lookup"><span data-stu-id="22563-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="22563-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="22563-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="22563-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="22563-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="22563-108">Effet de mesure permettant de déclarer la probabilité de, exprimée sous la forme d’un opérateur qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="22563-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="22563-109">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="22563-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="22563-110">Registre sur lequel effectuer l’assertion.</span><span class="sxs-lookup"><span data-stu-id="22563-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="22563-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="22563-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="22563-112">Résultat attendu de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="22563-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="22563-113">sonde : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22563-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="22563-114">Probabilité avec laquelle le résultat donné est attendu.</span><span class="sxs-lookup"><span data-stu-id="22563-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="22563-115">MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="22563-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="22563-116">Message à signaler si l’assertion échoue.</span><span class="sxs-lookup"><span data-stu-id="22563-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="22563-117">tol : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22563-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="22563-118">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22563-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="22563-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="22563-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="22563-120">Notes</span><span class="sxs-lookup"><span data-stu-id="22563-120">Remarks</span></span>

<span data-ttu-id="22563-121">Notez que les versions adjacentes et contrôlées de cette opération ne vérifient pas la condition.</span><span class="sxs-lookup"><span data-stu-id="22563-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="22563-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22563-122">See Also</span></span>

- [<span data-ttu-id="22563-123">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="22563-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)