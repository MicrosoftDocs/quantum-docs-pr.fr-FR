---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Opération ComputeReciprocalFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843259"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="92762-102">Opération ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="92762-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="92762-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="92762-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="92762-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="92762-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="92762-105">Calcule $1/x $ pour un nombre à virgule fixe $x $.</span><span class="sxs-lookup"><span data-stu-id="92762-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="92762-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="92762-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="92762-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="92762-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="92762-108">Nombre à virgule fixe à inverser.</span><span class="sxs-lookup"><span data-stu-id="92762-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="92762-109">résultat : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="92762-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="92762-110">Nombre à virgule fixe qui contiendra le résultat.</span><span class="sxs-lookup"><span data-stu-id="92762-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="92762-111">Doit être initialisé à $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="92762-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="92762-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92762-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

