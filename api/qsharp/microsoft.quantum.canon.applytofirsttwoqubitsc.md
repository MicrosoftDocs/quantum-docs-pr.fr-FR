---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Opération ApplyToFirstTwoQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 97706ffcc8700a0055ff37bbbaccc6fb4f8854b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704806"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="77b0e-102">Opération ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="77b0e-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="77b0e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="77b0e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="77b0e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77b0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="77b0e-105">Applique une opération aux deux premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="77b0e-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="77b0e-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="77b0e-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="77b0e-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="77b0e-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="77b0e-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77b0e-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="77b0e-109">Une opération à appliquer aux deux premiers qubits</span><span class="sxs-lookup"><span data-stu-id="77b0e-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="77b0e-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="77b0e-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="77b0e-111">Tableau qubit vers les deux premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="77b0e-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="77b0e-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77b0e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="77b0e-113">Notes</span><span class="sxs-lookup"><span data-stu-id="77b0e-113">Remarks</span></span>

<span data-ttu-id="77b0e-114">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="77b0e-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="77b0e-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77b0e-115">See Also</span></span>

- [<span data-ttu-id="77b0e-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="77b0e-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)