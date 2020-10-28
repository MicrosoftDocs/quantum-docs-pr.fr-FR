---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Opération AssertMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702781"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="b6fac-102">Opération AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="b6fac-102">AssertMeasurement operation</span></span>

<span data-ttu-id="b6fac-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b6fac-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b6fac-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6fac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6fac-105">Les assertions qui mesurent le qubits donné dans la base Pauli donnée auront toujours le résultat donné.</span><span class="sxs-lookup"><span data-stu-id="b6fac-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b6fac-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b6fac-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="b6fac-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b6fac-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="b6fac-108">Effet de mesure permettant de déclarer la probabilité de, exprimée sous la forme d’un opérateur qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="b6fac-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b6fac-109">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b6fac-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b6fac-110">Registre sur lequel effectuer l’assertion.</span><span class="sxs-lookup"><span data-stu-id="b6fac-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="b6fac-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="b6fac-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="b6fac-112">Résultat attendu de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="b6fac-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="b6fac-113">MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b6fac-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b6fac-114">Message à signaler si l’assertion échoue.</span><span class="sxs-lookup"><span data-stu-id="b6fac-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6fac-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6fac-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b6fac-116">Notes</span><span class="sxs-lookup"><span data-stu-id="b6fac-116">Remarks</span></span>

<span data-ttu-id="b6fac-117">Notez que les versions adjacentes et contrôlées de cette opération ne vérifient pas la condition.</span><span class="sxs-lookup"><span data-stu-id="b6fac-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6fac-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b6fac-118">See Also</span></span>

- [<span data-ttu-id="b6fac-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="b6fac-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)