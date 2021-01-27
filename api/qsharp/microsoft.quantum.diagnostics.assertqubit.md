---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Opération AssertQubit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853452"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="e92e7-102">Opération AssertQubit</span><span class="sxs-lookup"><span data-stu-id="e92e7-102">AssertQubit operation</span></span>

<span data-ttu-id="e92e7-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e92e7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e92e7-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e92e7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e92e7-105">Déclare que qubit `q` se trouve dans le eigenstate attendu de l’opérateur Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="e92e7-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e92e7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e92e7-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="e92e7-107">ATTENDU : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="e92e7-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="e92e7-108">Dans quel état le qubit doit être dans : `Zero` ou `One` .</span><span class="sxs-lookup"><span data-stu-id="e92e7-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="e92e7-109">q : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e92e7-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e92e7-110">Qubit dont l’État est déclaré.</span><span class="sxs-lookup"><span data-stu-id="e92e7-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e92e7-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e92e7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e92e7-112">Notes</span><span class="sxs-lookup"><span data-stu-id="e92e7-112">Remarks</span></span>

<span data-ttu-id="e92e7-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permet d’déclarer des États qubit arbitraires plutôt que $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="e92e7-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="e92e7-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e92e7-114">See Also</span></span>

- [<span data-ttu-id="e92e7-115">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="e92e7-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)