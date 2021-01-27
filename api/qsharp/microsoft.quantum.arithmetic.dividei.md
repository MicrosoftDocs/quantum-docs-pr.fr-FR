---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Opération de division
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846679"
---
# <a name="dividei-operation"></a><span data-ttu-id="c0164-102">Opération de division</span><span class="sxs-lookup"><span data-stu-id="c0164-102">DivideI operation</span></span>

<span data-ttu-id="c0164-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c0164-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c0164-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c0164-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c0164-105">Divise deux entiers quantiques.</span><span class="sxs-lookup"><span data-stu-id="c0164-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c0164-106">Description</span><span class="sxs-lookup"><span data-stu-id="c0164-106">Description</span></span>

<span data-ttu-id="c0164-107">`xs` contiendra le reste `xs - floor(xs/ys) * ys` et contiendra `result` `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="c0164-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="c0164-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c0164-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c0164-109">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c0164-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c0164-110">$n dividende de $ bits, sera remplacé par le reste.</span><span class="sxs-lookup"><span data-stu-id="c0164-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c0164-111">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c0164-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c0164-112">diviseur de $n $ bits</span><span class="sxs-lookup"><span data-stu-id="c0164-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="c0164-113">résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c0164-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c0164-114">$n résultat de $ bits, doit être initialement dans l’État $ \ket {0} $ et sera remplacé par le résultat de la Division d’entier.</span><span class="sxs-lookup"><span data-stu-id="c0164-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0164-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0164-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c0164-116">Notes</span><span class="sxs-lookup"><span data-stu-id="c0164-116">Remarks</span></span>

<span data-ttu-id="c0164-117">Utilise une approche standard de décalage et de soustraction pour implémenter la Division.</span><span class="sxs-lookup"><span data-stu-id="c0164-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="c0164-118">La version contrôlée est spécialisée, de sorte que la soustraction ne nécessite pas de contrôles supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c0164-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>