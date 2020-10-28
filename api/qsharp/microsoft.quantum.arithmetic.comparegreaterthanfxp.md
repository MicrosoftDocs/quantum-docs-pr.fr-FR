---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Opération CompareGreaterThanFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707395"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="8ea23-102">Opération CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="8ea23-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="8ea23-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8ea23-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8ea23-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ea23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ea23-105">Compare deux nombres à virgule fixe stockés dans des registres quantiques et contrôle un retournement sur le résultat.</span><span class="sxs-lookup"><span data-stu-id="8ea23-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8ea23-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="8ea23-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="8ea23-107">FP1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="8ea23-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="8ea23-108">Premier nombre à virgule fixe à comparer.</span><span class="sxs-lookup"><span data-stu-id="8ea23-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="8ea23-109">FP2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="8ea23-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="8ea23-110">Deuxième nombre à virgule fixe à comparer.</span><span class="sxs-lookup"><span data-stu-id="8ea23-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="8ea23-111">résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8ea23-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8ea23-112">Résultat de la comparaison.</span><span class="sxs-lookup"><span data-stu-id="8ea23-112">Result of the comparison.</span></span> <span data-ttu-id="8ea23-113">Est retourné si `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="8ea23-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ea23-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ea23-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8ea23-115">Notes</span><span class="sxs-lookup"><span data-stu-id="8ea23-115">Remarks</span></span>

<span data-ttu-id="8ea23-116">L’implémentation actuelle requiert que les deux nombres à virgule fixe aient la même position de point et le même nombre d’qubits.</span><span class="sxs-lookup"><span data-stu-id="8ea23-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>