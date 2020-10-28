---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Fonction diagonale
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706118"
---
# <a name="diagonal-function"></a><span data-ttu-id="21676-102">Fonction diagonale</span><span class="sxs-lookup"><span data-stu-id="21676-102">Diagonal function</span></span>

<span data-ttu-id="21676-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="21676-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="21676-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21676-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21676-105">Retourne un tableau d’éléments Diagonal d’un tableau à deux dimensions</span><span class="sxs-lookup"><span data-stu-id="21676-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="21676-106">Description</span><span class="sxs-lookup"><span data-stu-id="21676-106">Description</span></span>

<span data-ttu-id="21676-107">Si le tableau à deux dimensions n’a pas de forme carrée, la diagonale sur le nombre minimal de lignes et de colonnes est retournée.</span><span class="sxs-lookup"><span data-stu-id="21676-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="21676-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="21676-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="21676-109">matrice : 't [] []</span><span class="sxs-lookup"><span data-stu-id="21676-109">matrix : 'T[][]</span></span>

<span data-ttu-id="21676-110">matrice à deux dimensions dans l’ordre des lignes</span><span class="sxs-lookup"><span data-stu-id="21676-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="21676-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="21676-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="21676-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="21676-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="21676-113">Peut</span><span class="sxs-lookup"><span data-stu-id="21676-113">'T</span></span>

<span data-ttu-id="21676-114">Type de chaque élément de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="21676-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="21676-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21676-115">See Also</span></span>

- [<span data-ttu-id="21676-116">Microsoft. Quantum. Arrays. transpose</span><span class="sxs-lookup"><span data-stu-id="21676-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)