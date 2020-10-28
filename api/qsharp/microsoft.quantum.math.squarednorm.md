---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709089"
---
# <a name="squarednorm-function"></a><span data-ttu-id="52522-102">SquaredNorm fonction)</span><span class="sxs-lookup"><span data-stu-id="52522-102">SquaredNorm function</span></span>

<span data-ttu-id="52522-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="52522-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="52522-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52522-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52522-105">Retourne le carré 2-norme d’un vecteur.</span><span class="sxs-lookup"><span data-stu-id="52522-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="52522-106">Description</span><span class="sxs-lookup"><span data-stu-id="52522-106">Description</span></span>

<span data-ttu-id="52522-107">Retourne le carré 2-norme d’un vecteur ; autrement dit, étant donné une entrée $ \vec{x} $, retourne $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="52522-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="52522-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="52522-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="52522-109">Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="52522-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="52522-110">Vecteur dont la norme quadratique 2 doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="52522-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="52522-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="52522-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="52522-112">La norme quadratique 2 de `array` .</span><span class="sxs-lookup"><span data-stu-id="52522-112">The squared 2-norm of `array`.</span></span>