---
uid: Microsoft.Quantum.Arrays.Zipped
title: Fonction zippée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845347"
---
# <a name="zipped-function"></a><span data-ttu-id="94a60-102">Fonction zippée</span><span class="sxs-lookup"><span data-stu-id="94a60-102">Zipped function</span></span>

<span data-ttu-id="94a60-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="94a60-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="94a60-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94a60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94a60-105">À partir de deux tableaux, retourne un nouveau tableau de paires de sorte que chaque paire contient un élément de chaque tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="94a60-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="94a60-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="94a60-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="94a60-107">gauche : 't []</span><span class="sxs-lookup"><span data-stu-id="94a60-107">left : 'T[]</span></span>

<span data-ttu-id="94a60-108">Tableau contenant des valeurs pour le premier élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="94a60-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="94a60-109">droite : 'U []</span><span class="sxs-lookup"><span data-stu-id="94a60-109">right : 'U[]</span></span>

<span data-ttu-id="94a60-110">Tableau contenant les valeurs du deuxième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="94a60-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="94a60-111">Sortie : ('t, 'U) []</span><span class="sxs-lookup"><span data-stu-id="94a60-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="94a60-112">Tableau contenant des paires de la forme `(left[idx], right[idx])` pour chacune `idx` .</span><span class="sxs-lookup"><span data-stu-id="94a60-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="94a60-113">Si les deux tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.</span><span class="sxs-lookup"><span data-stu-id="94a60-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="94a60-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="94a60-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94a60-115">Peut</span><span class="sxs-lookup"><span data-stu-id="94a60-115">'T</span></span>

<span data-ttu-id="94a60-116">Type des éléments du tableau de gauche.</span><span class="sxs-lookup"><span data-stu-id="94a60-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="94a60-117">'U</span><span class="sxs-lookup"><span data-stu-id="94a60-117">'U</span></span>

<span data-ttu-id="94a60-118">Type des éléments du tableau de droite.</span><span class="sxs-lookup"><span data-stu-id="94a60-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="94a60-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="94a60-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="94a60-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94a60-120">See Also</span></span>

- [<span data-ttu-id="94a60-121">Microsoft.Quantum.Arrays.ZipPED3</span><span class="sxs-lookup"><span data-stu-id="94a60-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="94a60-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="94a60-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="94a60-123">Microsoft. Quantum. tableaux. unzippé</span><span class="sxs-lookup"><span data-stu-id="94a60-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)