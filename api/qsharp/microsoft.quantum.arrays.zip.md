---
uid: Microsoft.Quantum.Arrays.Zip
title: Fonction zip
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850896"
---
# <a name="zip-function"></a><span data-ttu-id="a0776-102">Fonction zip</span><span class="sxs-lookup"><span data-stu-id="a0776-102">Zip function</span></span>

<span data-ttu-id="a0776-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0776-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0776-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a0776-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="a0776-105">Le fichier zip est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="a0776-105">Zip has been deprecated.</span></span> <span data-ttu-id="a0776-106">Utilisez plutôt <xref:Microsoft.Quantum.Arrays.Zipped>.</span><span class="sxs-lookup"><span data-stu-id="a0776-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="a0776-107">À partir de deux tableaux, retourne un nouveau tableau de paires de sorte que chaque paire contient un élément de chaque tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="a0776-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="a0776-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="a0776-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="a0776-109">gauche : 't []</span><span class="sxs-lookup"><span data-stu-id="a0776-109">left : 'T[]</span></span>

<span data-ttu-id="a0776-110">Tableau contenant des valeurs pour le premier élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="a0776-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="a0776-111">droite : 'U []</span><span class="sxs-lookup"><span data-stu-id="a0776-111">right : 'U[]</span></span>

<span data-ttu-id="a0776-112">Tableau contenant les valeurs du deuxième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="a0776-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="a0776-113">Sortie : ('t, 'U) []</span><span class="sxs-lookup"><span data-stu-id="a0776-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="a0776-114">Tableau contenant des paires de la forme `(left[idx], right[idx])` pour chacune `idx` .</span><span class="sxs-lookup"><span data-stu-id="a0776-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="a0776-115">Si les deux tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.</span><span class="sxs-lookup"><span data-stu-id="a0776-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a0776-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a0776-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a0776-117">Peut</span><span class="sxs-lookup"><span data-stu-id="a0776-117">'T</span></span>

<span data-ttu-id="a0776-118">Type des éléments du tableau de gauche.</span><span class="sxs-lookup"><span data-stu-id="a0776-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="a0776-119">'U</span><span class="sxs-lookup"><span data-stu-id="a0776-119">'U</span></span>

<span data-ttu-id="a0776-120">Type des éléments du tableau de droite.</span><span class="sxs-lookup"><span data-stu-id="a0776-120">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="a0776-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="a0776-121">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="a0776-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0776-122">See Also</span></span>

- [<span data-ttu-id="a0776-123">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="a0776-123">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="a0776-124">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="a0776-124">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="a0776-125">Microsoft. Quantum. tableaux. unzippé</span><span class="sxs-lookup"><span data-stu-id="a0776-125">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)