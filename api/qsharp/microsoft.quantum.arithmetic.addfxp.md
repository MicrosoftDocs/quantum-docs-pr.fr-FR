---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Opération AddFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843868"
---
# <a name="addfxp-operation"></a><span data-ttu-id="b0187-102">Opération AddFxP</span><span class="sxs-lookup"><span data-stu-id="b0187-102">AddFxP operation</span></span>

<span data-ttu-id="b0187-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b0187-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b0187-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b0187-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b0187-105">Ajoute deux nombres à virgule fixe stockés dans des registres quantiques.</span><span class="sxs-lookup"><span data-stu-id="b0187-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b0187-106">Description</span><span class="sxs-lookup"><span data-stu-id="b0187-106">Description</span></span>

<span data-ttu-id="b0187-107">À partir de deux registres à virgule fixe respectivement dans les États $ \ket{f_1} $ et $ \ket{f_2} $, exécute l’opération $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="b0187-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="b0187-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="b0187-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="b0187-109">FP1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b0187-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b0187-110">Premier nombre à virgule fixe</span><span class="sxs-lookup"><span data-stu-id="b0187-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="b0187-111">FP2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b0187-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b0187-112">Deuxième nombre à virgule fixe, sera mis à jour pour contenir la somme des deux entrées.</span><span class="sxs-lookup"><span data-stu-id="b0187-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0187-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0187-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b0187-114">Notes</span><span class="sxs-lookup"><span data-stu-id="b0187-114">Remarks</span></span>

<span data-ttu-id="b0187-115">Dans l’implémentation actuelle, les deux nombres à virgule fixe doivent avoir la même position de point que le bit le moins significatif, c.-à-d. $n _i $ et $p _i $ doit être égal.</span><span class="sxs-lookup"><span data-stu-id="b0187-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>