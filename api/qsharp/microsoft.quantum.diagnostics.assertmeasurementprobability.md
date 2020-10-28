---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Opération AssertMeasurementProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702757"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="66b1f-102">Opération AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="66b1f-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="66b1f-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="66b1f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="66b1f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="66b1f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="66b1f-105">Les assertions qui mesurent le qubits donné dans la base Pauli donnée auront le résultat donné avec la probabilité donnée, dans une certaine tolérance.</span><span class="sxs-lookup"><span data-stu-id="66b1f-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="66b1f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="66b1f-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="66b1f-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="66b1f-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="66b1f-108">Effet de mesure permettant de déclarer la probabilité de, exprimée sous la forme d’un opérateur qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="66b1f-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="66b1f-109">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="66b1f-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="66b1f-110">Registre sur lequel effectuer l’assertion.</span><span class="sxs-lookup"><span data-stu-id="66b1f-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="66b1f-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="66b1f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="66b1f-112">Résultat attendu de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="66b1f-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="66b1f-113">sonde : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="66b1f-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="66b1f-114">Probabilité avec laquelle le résultat donné est attendu.</span><span class="sxs-lookup"><span data-stu-id="66b1f-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="66b1f-115">MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="66b1f-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="66b1f-116">Message à signaler si l’assertion échoue.</span><span class="sxs-lookup"><span data-stu-id="66b1f-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="66b1f-117">tol : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="66b1f-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="66b1f-118">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66b1f-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="66b1f-119">Notes</span><span class="sxs-lookup"><span data-stu-id="66b1f-119">Remarks</span></span>

<span data-ttu-id="66b1f-120">Notez que les versions adjacentes et contrôlées de cette opération ne vérifient pas la condition.</span><span class="sxs-lookup"><span data-stu-id="66b1f-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="66b1f-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66b1f-121">See Also</span></span>

- [<span data-ttu-id="66b1f-122">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="66b1f-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)