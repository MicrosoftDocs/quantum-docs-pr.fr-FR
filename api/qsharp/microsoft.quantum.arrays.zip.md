---
uid: Microsoft.Quantum.Arrays.Zip
title: Fonction zip
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705683"
---
# <a name="zip-function"></a><span data-ttu-id="2599f-102">Fonction zip</span><span class="sxs-lookup"><span data-stu-id="2599f-102">Zip function</span></span>

<span data-ttu-id="2599f-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2599f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2599f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2599f-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="2599f-105">Le fichier zip est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="2599f-105">Zip has been deprecated.</span></span> <span data-ttu-id="2599f-106">Utilisez plutôt <xref:Microsoft.Quantum.Arrays.Zipped>.</span><span class="sxs-lookup"><span data-stu-id="2599f-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="2599f-107">À partir de deux tableaux, retourne un nouveau tableau de paires de sorte que chaque paire contient un élément de chaque tableau d’origine.</span><span class="sxs-lookup"><span data-stu-id="2599f-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="2599f-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="2599f-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="2599f-109">gauche : 't []</span><span class="sxs-lookup"><span data-stu-id="2599f-109">left : 'T[]</span></span>

<span data-ttu-id="2599f-110">Tableau contenant des valeurs pour le premier élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="2599f-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="2599f-111">droite : 'U []</span><span class="sxs-lookup"><span data-stu-id="2599f-111">right : 'U[]</span></span>

<span data-ttu-id="2599f-112">Tableau contenant les valeurs du deuxième élément de chaque tuple.</span><span class="sxs-lookup"><span data-stu-id="2599f-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="2599f-113">Sortie : ('t, 'U) []</span><span class="sxs-lookup"><span data-stu-id="2599f-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="2599f-114">Tableau contenant des paires de la forme `(left[idx], right[idx])` pour chacune `idx` .</span><span class="sxs-lookup"><span data-stu-id="2599f-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="2599f-115">Si les deux tableaux ne sont pas de longueur égale, la sortie sera aussi longue que la plus petite des entrées.</span><span class="sxs-lookup"><span data-stu-id="2599f-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2599f-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2599f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2599f-117">Peut</span><span class="sxs-lookup"><span data-stu-id="2599f-117">'T</span></span>

<span data-ttu-id="2599f-118">Type des éléments du tableau de gauche.</span><span class="sxs-lookup"><span data-stu-id="2599f-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="2599f-119">'U</span><span class="sxs-lookup"><span data-stu-id="2599f-119">'U</span></span>

<span data-ttu-id="2599f-120">Type des éléments du tableau de droite.</span><span class="sxs-lookup"><span data-stu-id="2599f-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2599f-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2599f-121">See Also</span></span>

- [<span data-ttu-id="2599f-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="2599f-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="2599f-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="2599f-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="2599f-124">Microsoft. Quantum. tableaux. unzippé</span><span class="sxs-lookup"><span data-stu-id="2599f-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)