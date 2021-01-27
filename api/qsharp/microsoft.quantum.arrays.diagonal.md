---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Fonction diagonale
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842825"
---
# <a name="diagonal-function"></a><span data-ttu-id="b7131-102">Fonction diagonale</span><span class="sxs-lookup"><span data-stu-id="b7131-102">Diagonal function</span></span>

<span data-ttu-id="b7131-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b7131-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b7131-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7131-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7131-105">Retourne un tableau d’éléments Diagonal d’un tableau à deux dimensions</span><span class="sxs-lookup"><span data-stu-id="b7131-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b7131-106">Description</span><span class="sxs-lookup"><span data-stu-id="b7131-106">Description</span></span>

<span data-ttu-id="b7131-107">Si le tableau à deux dimensions n’a pas de forme carrée, la diagonale sur le nombre minimal de lignes et de colonnes est retournée.</span><span class="sxs-lookup"><span data-stu-id="b7131-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="b7131-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="b7131-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="b7131-109">matrice : 't [] []</span><span class="sxs-lookup"><span data-stu-id="b7131-109">matrix : 'T[][]</span></span>

<span data-ttu-id="b7131-110">matrice à deux dimensions dans l’ordre des lignes</span><span class="sxs-lookup"><span data-stu-id="b7131-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="b7131-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="b7131-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b7131-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b7131-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b7131-113">Peut</span><span class="sxs-lookup"><span data-stu-id="b7131-113">'T</span></span>

<span data-ttu-id="b7131-114">Type de chaque élément de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="b7131-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="b7131-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="b7131-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="b7131-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7131-116">See Also</span></span>

- [<span data-ttu-id="b7131-117">Microsoft. Quantum. Arrays. transpose</span><span class="sxs-lookup"><span data-stu-id="b7131-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)