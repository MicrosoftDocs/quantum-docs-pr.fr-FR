---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848214"
---
# <a name="squarednorm-function"></a><span data-ttu-id="ba319-102">SquaredNorm fonction)</span><span class="sxs-lookup"><span data-stu-id="ba319-102">SquaredNorm function</span></span>

<span data-ttu-id="ba319-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ba319-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ba319-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba319-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba319-105">Retourne le carré 2-norme d’un vecteur.</span><span class="sxs-lookup"><span data-stu-id="ba319-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="ba319-106">Description</span><span class="sxs-lookup"><span data-stu-id="ba319-106">Description</span></span>

<span data-ttu-id="ba319-107">Retourne le carré 2-norme d’un vecteur ; autrement dit, étant donné une entrée $ \vec{x} $, retourne $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="ba319-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="ba319-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="ba319-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="ba319-109">Tableau : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ba319-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ba319-110">Vecteur dont la norme quadratique 2 doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="ba319-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="ba319-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ba319-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ba319-112">La norme quadratique 2 de `array` .</span><span class="sxs-lookup"><span data-stu-id="ba319-112">The squared 2-norm of `array`.</span></span>