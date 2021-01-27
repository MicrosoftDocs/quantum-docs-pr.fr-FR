---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Opération AssertMeasurement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853500"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="6179f-102">Opération AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="6179f-102">AssertMeasurement operation</span></span>

<span data-ttu-id="6179f-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6179f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6179f-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6179f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6179f-105">Les assertions qui mesurent le qubits donné dans la base Pauli donnée auront toujours le résultat donné.</span><span class="sxs-lookup"><span data-stu-id="6179f-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6179f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6179f-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="6179f-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="6179f-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="6179f-108">Effet de mesure permettant de déclarer la probabilité de, exprimée sous la forme d’un opérateur qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="6179f-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6179f-109">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6179f-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6179f-110">Registre sur lequel effectuer l’assertion.</span><span class="sxs-lookup"><span data-stu-id="6179f-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="6179f-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="6179f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="6179f-112">Résultat attendu de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="6179f-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="6179f-113">MSG : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6179f-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6179f-114">Message à signaler si l’assertion échoue.</span><span class="sxs-lookup"><span data-stu-id="6179f-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6179f-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6179f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6179f-116">Notes</span><span class="sxs-lookup"><span data-stu-id="6179f-116">Remarks</span></span>

<span data-ttu-id="6179f-117">Notez que les versions adjacentes et contrôlées de cette opération ne vérifient pas la condition.</span><span class="sxs-lookup"><span data-stu-id="6179f-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="6179f-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6179f-118">See Also</span></span>

- [<span data-ttu-id="6179f-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="6179f-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)