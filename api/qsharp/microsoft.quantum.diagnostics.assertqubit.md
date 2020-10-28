---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Opération AssertQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702742"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="0ae98-102">Opération AssertQubit</span><span class="sxs-lookup"><span data-stu-id="0ae98-102">AssertQubit operation</span></span>

<span data-ttu-id="0ae98-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0ae98-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0ae98-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0ae98-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0ae98-105">Déclare que qubit `q` se trouve dans le eigenstate attendu de l’opérateur Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="0ae98-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0ae98-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0ae98-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="0ae98-107">ATTENDU : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="0ae98-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="0ae98-108">Dans quel état le qubit doit être dans : `Zero` ou `One` .</span><span class="sxs-lookup"><span data-stu-id="0ae98-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="0ae98-109">q : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0ae98-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0ae98-110">Qubit dont l’État est déclaré.</span><span class="sxs-lookup"><span data-stu-id="0ae98-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0ae98-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ae98-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0ae98-112">Notes</span><span class="sxs-lookup"><span data-stu-id="0ae98-112">Remarks</span></span>

<span data-ttu-id="0ae98-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permet d’déclarer des États qubit arbitraires plutôt que $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="0ae98-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ae98-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ae98-114">See Also</span></span>

- [<span data-ttu-id="0ae98-115">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="0ae98-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)