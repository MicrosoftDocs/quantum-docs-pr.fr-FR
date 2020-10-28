---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Opération ApplyToFirstThreeQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704862"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="780b0-102">Opération ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="780b0-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="780b0-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="780b0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="780b0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="780b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="780b0-105">Applique une opération aux trois premiers qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="780b0-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="780b0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="780b0-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="780b0-107">OP : ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="780b0-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="780b0-108">Une opération à appliquer aux trois premiers qubits</span><span class="sxs-lookup"><span data-stu-id="780b0-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="780b0-109">Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="780b0-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="780b0-110">Tableau qubit sur les trois premiers qubits desquels l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="780b0-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="780b0-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="780b0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="780b0-112">Notes</span><span class="sxs-lookup"><span data-stu-id="780b0-112">Remarks</span></span>

<span data-ttu-id="780b0-113">Ceci équivaut à :</span><span class="sxs-lookup"><span data-stu-id="780b0-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="780b0-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="780b0-114">See Also</span></span>

- [<span data-ttu-id="780b0-115">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="780b0-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="780b0-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="780b0-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="780b0-117">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="780b0-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)