---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707922"
---
# <a name="pnorm-function"></a><span data-ttu-id="e81f3-102">PNorm fonction)</span><span class="sxs-lookup"><span data-stu-id="e81f3-102">PNorm function</span></span>

<span data-ttu-id="e81f3-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e81f3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e81f3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e81f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e81f3-105">Retourne la `L(p)` norme d’un vecteur de `Double` s.</span><span class="sxs-lookup"><span data-stu-id="e81f3-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="e81f3-106">Autrement dit, étant donné un tableau $x $ de type `Double[]` , le $p $-normal $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $ est retourné.</span><span class="sxs-lookup"><span data-stu-id="e81f3-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="e81f3-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e81f3-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="e81f3-108">p : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e81f3-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e81f3-109">L’exposant $p $ dans le $p $-normal.</span><span class="sxs-lookup"><span data-stu-id="e81f3-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="e81f3-110">Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e81f3-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="e81f3-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e81f3-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e81f3-112">$P $-normal $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="e81f3-112">The $p$-norm $\|x\|_p$.</span></span>