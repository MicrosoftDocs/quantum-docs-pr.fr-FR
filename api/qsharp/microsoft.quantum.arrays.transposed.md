---
uid: Microsoft.Quantum.Arrays.Transposed
title: Fonction transposée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705739"
---
# <a name="transposed-function"></a><span data-ttu-id="5bc3f-102">Fonction transposée</span><span class="sxs-lookup"><span data-stu-id="5bc3f-102">Transposed function</span></span>

<span data-ttu-id="5bc3f-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5bc3f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5bc3f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5bc3f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5bc3f-105">Retourne la transposer d’une matrice représentée sous la forme d’un tableau de tableaux.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="5bc3f-106">Description</span><span class="sxs-lookup"><span data-stu-id="5bc3f-106">Description</span></span>

<span data-ttu-id="5bc3f-107">Entrée en tant que $r \times c $ Matrix avec $r $ Rows et $c $ Columns.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="5bc3f-108">La matrice est basée sur des lignes, c.-à-d., `matrix[i][j]` accède à l’élément à la ligne $i $ et column $j $.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="5bc3f-109">Cette fonction retourne la matrice de $c \times r $ qui est le transposant de la matrice d’entrée.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="5bc3f-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="5bc3f-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="5bc3f-111">matrice : 't [] []</span><span class="sxs-lookup"><span data-stu-id="5bc3f-111">matrix : 'T[][]</span></span>

<span data-ttu-id="5bc3f-112">$R basée sur les lignes \times c $ Matrix</span><span class="sxs-lookup"><span data-stu-id="5bc3f-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="5bc3f-113">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="5bc3f-113">Output : 'T[][]</span></span>

<span data-ttu-id="5bc3f-114">$C de la matrice r $ \times transposée</span><span class="sxs-lookup"><span data-stu-id="5bc3f-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5bc3f-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="5bc3f-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5bc3f-116">Peut</span><span class="sxs-lookup"><span data-stu-id="5bc3f-116">'T</span></span>

<span data-ttu-id="5bc3f-117">Type de chaque élément de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="5bc3f-117">The type of each element of `matrix`.</span></span>