---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Opération AssertQubitWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202190"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="fdd54-102">Opération AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="fdd54-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="fdd54-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fdd54-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fdd54-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fdd54-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fdd54-105">Déclare que qubit `q` se trouve dans le eigenstate attendu de l’opérateur Z Pauli jusqu’à une tolérance donnée.</span><span class="sxs-lookup"><span data-stu-id="fdd54-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="fdd54-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fdd54-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="fdd54-107">ATTENDU : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="fdd54-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="fdd54-108">Dans quel état le qubit doit être dans : `Zero` ou `One` .</span><span class="sxs-lookup"><span data-stu-id="fdd54-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="fdd54-109">q : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fdd54-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fdd54-110">Qubit dont l’État est déclaré.</span><span class="sxs-lookup"><span data-stu-id="fdd54-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="fdd54-111">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fdd54-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fdd54-112">Tolérance sur la probabilité d’une mesure de la qubit qui retourne le résultat attendu.</span><span class="sxs-lookup"><span data-stu-id="fdd54-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fdd54-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fdd54-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fdd54-114">Notes</span><span class="sxs-lookup"><span data-stu-id="fdd54-114">Remarks</span></span>

<span data-ttu-id="fdd54-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permet d’déclarer des États qubit arbitraires plutôt que $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="fdd54-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdd54-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdd54-116">See Also</span></span>

- [<span data-ttu-id="fdd54-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="fdd54-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)