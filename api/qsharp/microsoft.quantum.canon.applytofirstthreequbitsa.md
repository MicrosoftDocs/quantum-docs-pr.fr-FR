---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: Opération ApplyToFirstThreeQubitsA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 502d876df0ed643c40ce6ee48eaf496a90b0f5dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704854"
---
# <a name="applytofirstthreequbitsa-operation"></a><span data-ttu-id="e53a5-102">Opération ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="e53a5-102">ApplyToFirstThreeQubitsA operation</span></span>

<span data-ttu-id="e53a5-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e53a5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e53a5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e53a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e53a5-105">Applique une opération aux trois premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="e53a5-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="e53a5-106">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="e53a5-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e53a5-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e53a5-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj"></a><span data-ttu-id="e53a5-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e53a5-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e53a5-109">Une opération à appliquer aux trois premiers qubits</span><span class="sxs-lookup"><span data-stu-id="e53a5-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e53a5-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e53a5-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e53a5-111">Tableau qubit sur les trois premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="e53a5-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e53a5-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e53a5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e53a5-113">Notes</span><span class="sxs-lookup"><span data-stu-id="e53a5-113">Remarks</span></span>

<span data-ttu-id="e53a5-114">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="e53a5-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="e53a5-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e53a5-115">See Also</span></span>

- [<span data-ttu-id="e53a5-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="e53a5-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)