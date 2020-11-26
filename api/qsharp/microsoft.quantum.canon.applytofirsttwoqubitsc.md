---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Opération ApplyToFirstTwoQubitsC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 6b6ee5f05ace92c15ce2038e2fedbaa2fee3dcc9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217354"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="110b6-102">Opération ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="110b6-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="110b6-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="110b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="110b6-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="110b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="110b6-105">Applique une opération aux deux premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="110b6-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="110b6-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="110b6-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="110b6-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="110b6-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="110b6-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="110b6-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="110b6-109">Une opération à appliquer aux deux premiers qubits</span><span class="sxs-lookup"><span data-stu-id="110b6-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="110b6-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="110b6-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="110b6-111">Tableau qubit vers les deux premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="110b6-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="110b6-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="110b6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="110b6-113">Notes</span><span class="sxs-lookup"><span data-stu-id="110b6-113">Remarks</span></span>

<span data-ttu-id="110b6-114">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="110b6-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="110b6-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="110b6-115">See Also</span></span>

- [<span data-ttu-id="110b6-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="110b6-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)