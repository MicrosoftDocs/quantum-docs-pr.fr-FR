---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Opération MultiplyFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222607"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="014c9-102">Opération MultiplyFxP</span><span class="sxs-lookup"><span data-stu-id="014c9-102">MultiplyFxP operation</span></span>

<span data-ttu-id="014c9-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="014c9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="014c9-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="014c9-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="014c9-105">Multiplie deux nombres à virgule fixe dans des registres quantiques.</span><span class="sxs-lookup"><span data-stu-id="014c9-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="014c9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="014c9-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="014c9-107">FP1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="014c9-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="014c9-108">Premier nombre à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="014c9-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="014c9-109">FP2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="014c9-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="014c9-110">Deuxième nombre à virgule fixe.</span><span class="sxs-lookup"><span data-stu-id="014c9-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="014c9-111">résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="014c9-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="014c9-112">Nombre à virgule fixe du résultat, doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="014c9-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="014c9-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="014c9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="014c9-114">Notes</span><span class="sxs-lookup"><span data-stu-id="014c9-114">Remarks</span></span>

<span data-ttu-id="014c9-115">L’implémentation actuelle requiert que les trois nombres à virgule fixe aient la même position de point et le même nombre d’qubits.</span><span class="sxs-lookup"><span data-stu-id="014c9-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>