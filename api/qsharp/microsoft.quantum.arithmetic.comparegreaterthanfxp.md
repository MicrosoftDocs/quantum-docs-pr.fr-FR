---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Opération CompareGreaterThanFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843323"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="01682-102">Opération CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="01682-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="01682-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="01682-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="01682-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="01682-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="01682-105">Compare deux nombres à virgule fixe stockés dans des registres quantiques et contrôle un retournement sur le résultat.</span><span class="sxs-lookup"><span data-stu-id="01682-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="01682-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="01682-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="01682-107">FP1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="01682-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="01682-108">Premier nombre à virgule fixe à comparer.</span><span class="sxs-lookup"><span data-stu-id="01682-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="01682-109">FP2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="01682-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="01682-110">Deuxième nombre à virgule fixe à comparer.</span><span class="sxs-lookup"><span data-stu-id="01682-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="01682-111">résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="01682-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="01682-112">Résultat de la comparaison.</span><span class="sxs-lookup"><span data-stu-id="01682-112">Result of the comparison.</span></span> <span data-ttu-id="01682-113">Est retourné si `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="01682-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="01682-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01682-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="01682-115">Notes</span><span class="sxs-lookup"><span data-stu-id="01682-115">Remarks</span></span>

<span data-ttu-id="01682-116">L’implémentation actuelle requiert que les deux nombres à virgule fixe aient la même position de point et le même nombre d’qubits.</span><span class="sxs-lookup"><span data-stu-id="01682-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>