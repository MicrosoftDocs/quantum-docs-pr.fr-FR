---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Opération de multiplication
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706371"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="975e2-102">Opération de multiplication</span><span class="sxs-lookup"><span data-stu-id="975e2-102">MultiplyI operation</span></span>

<span data-ttu-id="975e2-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="975e2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="975e2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="975e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="975e2-105">Multipliez `xs` l’entier par `ys` un entier et stockez le résultat dans `result` , qui doit être initialement égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="975e2-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="975e2-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="975e2-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="975e2-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="975e2-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="975e2-108">$n multiplicande $-bit (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="975e2-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="975e2-109">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="975e2-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="975e2-110">$n (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="975e2-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="975e2-111">résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="975e2-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="975e2-112">résultat de $2n $-bit (LittleEndian), doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="975e2-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="975e2-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="975e2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="975e2-114">Notes</span><span class="sxs-lookup"><span data-stu-id="975e2-114">Remarks</span></span>

<span data-ttu-id="975e2-115">Utilise une approche standard Shift-and-Add pour implémenter la multiplication.</span><span class="sxs-lookup"><span data-stu-id="975e2-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="975e2-116">La version contrôlée a été améliorée par la copie des $x _i $ dans un Ancilla qubit conditionnel sur le qubits de contrôle, puis en contrôlant l’ajout sur le qubit Ancilla.</span><span class="sxs-lookup"><span data-stu-id="975e2-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>