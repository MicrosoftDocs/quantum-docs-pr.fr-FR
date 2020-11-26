---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227520"
---
# <a name="pnormalized-function"></a><span data-ttu-id="3690f-102">PNormalized fonction)</span><span class="sxs-lookup"><span data-stu-id="3690f-102">PNormalized function</span></span>

<span data-ttu-id="3690f-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3690f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3690f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3690f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3690f-105">Normalise un vecteur de `Double` s dans la `L(p)` norme.</span><span class="sxs-lookup"><span data-stu-id="3690f-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="3690f-106">Autrement dit, étant donné un tableau $x $ de type `Double[]` , retourne un tableau où tous les éléments sont divisés par le $p $-normal $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="3690f-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="3690f-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="3690f-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="3690f-108">p : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3690f-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3690f-109">L’exposant $p $ dans le $p $-normal.</span><span class="sxs-lookup"><span data-stu-id="3690f-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="3690f-110">Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3690f-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="3690f-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3690f-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3690f-112">Le tableau $x $ normalized par la $p $-Normalize $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="3690f-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="3690f-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3690f-113">See Also</span></span>

- [<span data-ttu-id="3690f-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="3690f-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)