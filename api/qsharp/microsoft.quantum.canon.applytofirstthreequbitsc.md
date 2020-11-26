---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: Opération ApplyToFirstThreeQubitsC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: cb6945f5aa398d0bf6417c5cfd21142008a54b13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217439"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="605f0-102">Opération ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="605f0-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="605f0-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="605f0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="605f0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="605f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="605f0-105">Applique une opération aux trois premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="605f0-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="605f0-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="605f0-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="605f0-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="605f0-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-ctl"></a><span data-ttu-id="605f0-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="605f0-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="605f0-109">Une opération à appliquer aux trois premiers qubits</span><span class="sxs-lookup"><span data-stu-id="605f0-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="605f0-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="605f0-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="605f0-111">Tableau qubit sur les trois premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="605f0-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="605f0-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="605f0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="605f0-113">Notes</span><span class="sxs-lookup"><span data-stu-id="605f0-113">Remarks</span></span>

<span data-ttu-id="605f0-114">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="605f0-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="605f0-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="605f0-115">See Also</span></span>

- [<span data-ttu-id="605f0-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="605f0-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)