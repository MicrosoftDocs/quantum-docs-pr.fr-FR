---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854852"
---
# <a name="pnormalized-function"></a><span data-ttu-id="dd60c-102">PNormalized fonction)</span><span class="sxs-lookup"><span data-stu-id="dd60c-102">PNormalized function</span></span>

<span data-ttu-id="dd60c-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dd60c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dd60c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd60c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd60c-105">Normalise un vecteur de `Double` s dans la `L(p)` norme.</span><span class="sxs-lookup"><span data-stu-id="dd60c-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="dd60c-106">Autrement dit, étant donné un tableau $x $ de type `Double[]` , retourne un tableau où tous les éléments sont divisés par le $p $-normal $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="dd60c-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="dd60c-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="dd60c-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="dd60c-108">p : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dd60c-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dd60c-109">L’exposant $p $ dans le $p $-normal.</span><span class="sxs-lookup"><span data-stu-id="dd60c-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="dd60c-110">Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dd60c-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="dd60c-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dd60c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dd60c-112">Le tableau $x $ normalized par la $p $-Normalize $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="dd60c-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd60c-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd60c-113">See Also</span></span>

- [<span data-ttu-id="dd60c-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="dd60c-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)