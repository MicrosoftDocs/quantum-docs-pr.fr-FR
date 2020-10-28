---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Opération ComputeReciprocalI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707347"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="234e2-102">Opération ComputeReciprocalI</span><span class="sxs-lookup"><span data-stu-id="234e2-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="234e2-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="234e2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="234e2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="234e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="234e2-105">Calcule la valeur réciproque 1/x pour un entier non signé x à l’aide de la Division d’entiers.</span><span class="sxs-lookup"><span data-stu-id="234e2-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="234e2-106">Le résultat, interprété comme un entier, sera `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="234e2-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="234e2-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="234e2-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="234e2-108">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="234e2-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="234e2-109">entier non signé n bits</span><span class="sxs-lookup"><span data-stu-id="234e2-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="234e2-110">résultat : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="234e2-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="234e2-111">la sortie 2n bits doit se trouver au début de $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="234e2-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="234e2-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="234e2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="234e2-113">Notes</span><span class="sxs-lookup"><span data-stu-id="234e2-113">Remarks</span></span>

<span data-ttu-id="234e2-114">Pour l’entrée x = 0, la sortie sera tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="234e2-114">For the input x=0, the output will be all-ones.</span></span>