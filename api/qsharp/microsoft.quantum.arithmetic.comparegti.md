---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: Opération CompareGTI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: c60c2827060f4ef223ebaf80ccdef09faaf56098
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707387"
---
# <a name="comparegti-operation"></a><span data-ttu-id="535a4-102">Opération CompareGTI</span><span class="sxs-lookup"><span data-stu-id="535a4-102">CompareGTI operation</span></span>

<span data-ttu-id="535a4-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="535a4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="535a4-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="535a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="535a4-105">Wrapper pour une comparaison d’entiers : `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="535a4-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="535a4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="535a4-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="535a4-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="535a4-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="535a4-108">Premier $n nombre de bits</span><span class="sxs-lookup"><span data-stu-id="535a4-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="535a4-109">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="535a4-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="535a4-110">Deuxième $n nombre de $ bits</span><span class="sxs-lookup"><span data-stu-id="535a4-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="535a4-111">résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="535a4-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="535a4-112">Est retourné si $x > y</span><span class="sxs-lookup"><span data-stu-id="535a4-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="535a4-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="535a4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
