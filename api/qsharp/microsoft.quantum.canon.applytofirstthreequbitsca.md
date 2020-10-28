---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: Opération ApplyToFirstThreeQubitsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bd7a3ac260d370aae9da8691fcd34a8b6221d451
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704843"
---
# <a name="applytofirstthreequbitsca-operation"></a><span data-ttu-id="f5596-102">Opération ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="f5596-102">ApplyToFirstThreeQubitsCA operation</span></span>

<span data-ttu-id="f5596-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f5596-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f5596-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5596-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5596-105">Applique une opération aux trois premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="f5596-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="f5596-106">Le modificateur `CA` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="f5596-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f5596-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="f5596-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj--ctl"></a><span data-ttu-id="f5596-108">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="f5596-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f5596-109">Une opération à appliquer aux trois premiers qubits</span><span class="sxs-lookup"><span data-stu-id="f5596-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f5596-110">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f5596-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f5596-111">Tableau qubit sur les trois premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="f5596-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5596-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5596-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f5596-113">Notes</span><span class="sxs-lookup"><span data-stu-id="f5596-113">Remarks</span></span>

<span data-ttu-id="f5596-114">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="f5596-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="f5596-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5596-115">See Also</span></span>

- [<span data-ttu-id="f5596-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="f5596-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)