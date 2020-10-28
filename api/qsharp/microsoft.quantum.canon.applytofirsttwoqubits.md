---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: Opération ApplyToFirstTwoQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: aad07889c0dbf2329304c98b06dbd0c225df8a81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704822"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="9001e-102">Opération ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="9001e-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="9001e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9001e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9001e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9001e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9001e-105">Applique une opération aux deux premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="9001e-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9001e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9001e-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="9001e-107">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9001e-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9001e-108">Une opération à appliquer aux deux premiers qubits</span><span class="sxs-lookup"><span data-stu-id="9001e-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="9001e-109">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9001e-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9001e-110">Tableau qubit vers les deux premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="9001e-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9001e-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9001e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9001e-112">Notes</span><span class="sxs-lookup"><span data-stu-id="9001e-112">Remarks</span></span>

<span data-ttu-id="9001e-113">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="9001e-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="9001e-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9001e-114">See Also</span></span>

- [<span data-ttu-id="9001e-115">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="9001e-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="9001e-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="9001e-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="9001e-117">Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="9001e-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)