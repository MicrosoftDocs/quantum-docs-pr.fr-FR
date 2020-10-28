---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Opération de division
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707342"
---
# <a name="dividei-operation"></a><span data-ttu-id="3bc1b-102">Opération de division</span><span class="sxs-lookup"><span data-stu-id="3bc1b-102">DivideI operation</span></span>

<span data-ttu-id="3bc1b-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3bc1b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3bc1b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3bc1b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3bc1b-105">Divise deux entiers quantiques.</span><span class="sxs-lookup"><span data-stu-id="3bc1b-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="3bc1b-106">Description</span><span class="sxs-lookup"><span data-stu-id="3bc1b-106">Description</span></span>

<span data-ttu-id="3bc1b-107">`xs` contiendra le reste `xs - floor(xs/ys) * ys` et contiendra `result` `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="3bc1b-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="3bc1b-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="3bc1b-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="3bc1b-109">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3bc1b-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3bc1b-110">$n dividende de $ bits, sera remplacé par le reste.</span><span class="sxs-lookup"><span data-stu-id="3bc1b-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="3bc1b-111">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3bc1b-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3bc1b-112">diviseur de $n $ bits</span><span class="sxs-lookup"><span data-stu-id="3bc1b-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="3bc1b-113">résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3bc1b-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3bc1b-114">$n résultat de $ bits, doit être initialement dans l’État $ \ket {0} $ et sera remplacé par le résultat de la Division d’entier.</span><span class="sxs-lookup"><span data-stu-id="3bc1b-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3bc1b-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3bc1b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3bc1b-116">Notes</span><span class="sxs-lookup"><span data-stu-id="3bc1b-116">Remarks</span></span>

<span data-ttu-id="3bc1b-117">Utilise une approche standard de décalage et de soustraction pour implémenter la Division.</span><span class="sxs-lookup"><span data-stu-id="3bc1b-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="3bc1b-118">La version contrôlée est spécialisée, de sorte que la soustraction ne nécessite pas de contrôles supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="3bc1b-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>