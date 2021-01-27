---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Opération de multiplication
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843024"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="f01b4-102">Opération de multiplication</span><span class="sxs-lookup"><span data-stu-id="f01b4-102">MultiplyI operation</span></span>

<span data-ttu-id="f01b4-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f01b4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f01b4-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f01b4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f01b4-105">Multipliez `xs` l’entier par `ys` un entier et stockez le résultat dans `result` , qui doit être initialement égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="f01b4-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f01b4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f01b4-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f01b4-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f01b4-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f01b4-108">$n multiplicande $-bit (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f01b4-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f01b4-109">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f01b4-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f01b4-110">$n (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f01b4-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="f01b4-111">résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f01b4-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f01b4-112">résultat de $2n $-bit (LittleEndian), doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="f01b4-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f01b4-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f01b4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f01b4-114">Notes</span><span class="sxs-lookup"><span data-stu-id="f01b4-114">Remarks</span></span>

<span data-ttu-id="f01b4-115">Utilise une approche standard Shift-and-Add pour implémenter la multiplication.</span><span class="sxs-lookup"><span data-stu-id="f01b4-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="f01b4-116">La version contrôlée a été améliorée par la copie des $x _i $ dans un Ancilla qubit conditionnel sur le qubits de contrôle, puis en contrôlant l’ajout sur le qubit Ancilla.</span><span class="sxs-lookup"><span data-stu-id="f01b4-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>