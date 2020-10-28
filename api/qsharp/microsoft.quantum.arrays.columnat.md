---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706166"
---
# <a name="columnat-function"></a><span data-ttu-id="9f714-102">ColumnAt fonction)</span><span class="sxs-lookup"><span data-stu-id="9f714-102">ColumnAt function</span></span>

<span data-ttu-id="9f714-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9f714-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9f714-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f714-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f714-105">Extrait une colonne d’une matrice.</span><span class="sxs-lookup"><span data-stu-id="9f714-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="9f714-106">Description</span><span class="sxs-lookup"><span data-stu-id="9f714-106">Description</span></span>

<span data-ttu-id="9f714-107">Cette fonction extrait une colonne dans une matrice dans l’ordre des lignes.</span><span class="sxs-lookup"><span data-stu-id="9f714-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="9f714-108">L’extraction d’une ligne corrsponds vers l’accès à l’élément du premier index et ne nécessite donc aucun traitement supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="9f714-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="9f714-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="9f714-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="9f714-110">colonne : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f714-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f714-111">Colonne de la matrice</span><span class="sxs-lookup"><span data-stu-id="9f714-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="9f714-112">matrice : 't [] []</span><span class="sxs-lookup"><span data-stu-id="9f714-112">matrix : 'T[][]</span></span>

<span data-ttu-id="9f714-113">matrice à deux dimensions dans l’ordre des lignes</span><span class="sxs-lookup"><span data-stu-id="9f714-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="9f714-114">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="9f714-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9f714-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9f714-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f714-116">Peut</span><span class="sxs-lookup"><span data-stu-id="9f714-116">'T</span></span>

<span data-ttu-id="9f714-117">Type de chaque élément de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="9f714-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f714-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f714-118">See Also</span></span>

- [<span data-ttu-id="9f714-119">Microsoft. Quantum. Arrays. transpose</span><span class="sxs-lookup"><span data-stu-id="9f714-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="9f714-120">Microsoft. Quantum. tableaux. Diagonal</span><span class="sxs-lookup"><span data-stu-id="9f714-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)