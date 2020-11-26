---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227299"
---
# <a name="squarednorm-function"></a><span data-ttu-id="9d9a3-102">SquaredNorm fonction)</span><span class="sxs-lookup"><span data-stu-id="9d9a3-102">SquaredNorm function</span></span>

<span data-ttu-id="9d9a3-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9d9a3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9d9a3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d9a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d9a3-105">Retourne le carré 2-norme d’un vecteur.</span><span class="sxs-lookup"><span data-stu-id="9d9a3-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="9d9a3-106">Description</span><span class="sxs-lookup"><span data-stu-id="9d9a3-106">Description</span></span>

<span data-ttu-id="9d9a3-107">Retourne le carré 2-norme d’un vecteur ; autrement dit, étant donné une entrée $ \vec{x} $, retourne $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="9d9a3-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="9d9a3-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="9d9a3-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="9d9a3-109">Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9d9a3-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9d9a3-110">Vecteur dont la norme quadratique 2 doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="9d9a3-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="9d9a3-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9d9a3-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9d9a3-112">La norme quadratique 2 de `array` .</span><span class="sxs-lookup"><span data-stu-id="9d9a3-112">The squared 2-norm of `array`.</span></span>