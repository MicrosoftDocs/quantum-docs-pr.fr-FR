---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Opération carrée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221859"
---
# <a name="squarei-operation"></a><span data-ttu-id="f478b-102">Opération carrée</span><span class="sxs-lookup"><span data-stu-id="f478b-102">SquareI operation</span></span>

<span data-ttu-id="f478b-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f478b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f478b-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f478b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f478b-105">Calcule le carré de l’entier `xs` dans `result` , qui doit être initialement égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="f478b-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f478b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f478b-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f478b-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f478b-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f478b-108">$n le nombre de $ bits au carré (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f478b-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="f478b-109">résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f478b-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f478b-110">résultat de $2n $-bit (LittleEndian), doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="f478b-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f478b-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f478b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f478b-112">Notes</span><span class="sxs-lookup"><span data-stu-id="f478b-112">Remarks</span></span>

<span data-ttu-id="f478b-113">Utilise une approche standard Shift-and-Add pour calculer le carré.</span><span class="sxs-lookup"><span data-stu-id="f478b-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="f478b-114">Enregistre $n-$1 qubits par rapport à la solution directe qui copie d’abord les XS avant l’application d’un multiplicateur normal, puis annule l’opération de copie.</span><span class="sxs-lookup"><span data-stu-id="f478b-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>