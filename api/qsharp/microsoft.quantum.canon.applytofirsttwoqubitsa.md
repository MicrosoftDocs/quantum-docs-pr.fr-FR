---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Opération ApplyToFirstTwoQubitsA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704819"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="0622b-102">Opération ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="0622b-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="0622b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0622b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0622b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0622b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0622b-105">Applique une opération aux deux premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="0622b-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="0622b-106">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="0622b-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0622b-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="0622b-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="0622b-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0622b-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0622b-109">Une opération à appliquer aux deux premiers qubits</span><span class="sxs-lookup"><span data-stu-id="0622b-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="0622b-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0622b-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0622b-111">Tableau qubit vers les deux premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="0622b-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0622b-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0622b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0622b-113">Notes</span><span class="sxs-lookup"><span data-stu-id="0622b-113">Remarks</span></span>

<span data-ttu-id="0622b-114">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="0622b-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="0622b-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0622b-115">See Also</span></span>

- [<span data-ttu-id="0622b-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="0622b-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)