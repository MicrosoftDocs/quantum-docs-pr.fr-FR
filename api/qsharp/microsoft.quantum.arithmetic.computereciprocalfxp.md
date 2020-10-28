---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Opération ComputeReciprocalFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707363"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="41134-102">Opération ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="41134-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="41134-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="41134-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="41134-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41134-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41134-105">Calcule $1/x $ pour un nombre à virgule fixe $x $.</span><span class="sxs-lookup"><span data-stu-id="41134-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="41134-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="41134-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="41134-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="41134-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="41134-108">Nombre à virgule fixe à inverser.</span><span class="sxs-lookup"><span data-stu-id="41134-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="41134-109">résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="41134-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="41134-110">Nombre à virgule fixe qui contiendra le résultat.</span><span class="sxs-lookup"><span data-stu-id="41134-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="41134-111">Doit être initialisé à $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="41134-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41134-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41134-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

