---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Opération carrée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 6813c8144b0ac98bae404b5e9b97e08b06c6bb3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846310"
---
# <a name="squarei-operation"></a><span data-ttu-id="488c6-102">Opération carrée</span><span class="sxs-lookup"><span data-stu-id="488c6-102">SquareI operation</span></span>

<span data-ttu-id="488c6-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="488c6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="488c6-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="488c6-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="488c6-105">Calcule le carré de l’entier `xs` dans `result` , qui doit être initialement égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="488c6-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="488c6-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="488c6-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="488c6-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="488c6-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="488c6-108">$n le nombre de $ bits au carré (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="488c6-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="488c6-109">résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="488c6-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="488c6-110">résultat de $2n $-bit (LittleEndian), doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="488c6-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="488c6-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="488c6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="488c6-112">Notes</span><span class="sxs-lookup"><span data-stu-id="488c6-112">Remarks</span></span>

<span data-ttu-id="488c6-113">Utilise une approche standard Shift-and-Add pour calculer le carré.</span><span class="sxs-lookup"><span data-stu-id="488c6-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="488c6-114">Enregistre $n-$1 qubits par rapport à la solution directe qui copie d’abord les XS avant l’application d’un multiplicateur normal, puis annule l’opération de copie.</span><span class="sxs-lookup"><span data-stu-id="488c6-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>