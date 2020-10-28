---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Opération carrée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706222"
---
# <a name="squarei-operation"></a><span data-ttu-id="79768-102">Opération carrée</span><span class="sxs-lookup"><span data-stu-id="79768-102">SquareI operation</span></span>

<span data-ttu-id="79768-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="79768-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="79768-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79768-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79768-105">Calcule le carré de l’entier `xs` dans `result` , qui doit être initialement égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="79768-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="79768-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="79768-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="79768-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="79768-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="79768-108">$n le nombre de $ bits au carré (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="79768-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="79768-109">résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="79768-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="79768-110">résultat de $2n $-bit (LittleEndian), doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="79768-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="79768-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79768-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="79768-112">Notes</span><span class="sxs-lookup"><span data-stu-id="79768-112">Remarks</span></span>

<span data-ttu-id="79768-113">Utilise une approche standard Shift-and-Add pour calculer le carré.</span><span class="sxs-lookup"><span data-stu-id="79768-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="79768-114">Enregistre $n-$1 qubits par rapport à la solution directe qui copie d’abord les XS avant l’application d’un multiplicateur normal, puis annule l’opération de copie.</span><span class="sxs-lookup"><span data-stu-id="79768-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>