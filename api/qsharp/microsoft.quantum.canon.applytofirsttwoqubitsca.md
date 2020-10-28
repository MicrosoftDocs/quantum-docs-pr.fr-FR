---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: Opération ApplyToFirstTwoQubitsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 0c5e29fbca8449f8122f2a9f988797e94e27da60
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704795"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="e8340-102">Opération ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="e8340-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="e8340-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e8340-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e8340-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8340-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8340-105">Applique une opération aux deux premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="e8340-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="e8340-106">Le modificateur `CA` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="e8340-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e8340-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e8340-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="e8340-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="e8340-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e8340-109">Une opération à appliquer aux deux premiers qubits</span><span class="sxs-lookup"><span data-stu-id="e8340-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e8340-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e8340-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e8340-111">Tableau qubit vers les deux premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="e8340-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8340-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8340-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e8340-113">Notes</span><span class="sxs-lookup"><span data-stu-id="e8340-113">Remarks</span></span>

<span data-ttu-id="e8340-114">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="e8340-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="e8340-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8340-115">See Also</span></span>

- [<span data-ttu-id="e8340-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="e8340-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)