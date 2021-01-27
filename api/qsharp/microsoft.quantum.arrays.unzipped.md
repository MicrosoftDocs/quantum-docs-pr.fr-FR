---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Fonction unzippée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845383"
---
# <a name="unzipped-function"></a><span data-ttu-id="42f02-102">Fonction unzippée</span><span class="sxs-lookup"><span data-stu-id="42f02-102">Unzipped function</span></span>

<span data-ttu-id="42f02-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="42f02-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="42f02-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42f02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42f02-105">À partir d’un tableau de 2 tuples, retourne un tuple de deux tableaux, chacun contenant les éléments des tuples du tableau d’entrée.</span><span class="sxs-lookup"><span data-stu-id="42f02-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="42f02-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="42f02-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="42f02-107">ARR : ('t, 'U) []</span><span class="sxs-lookup"><span data-stu-id="42f02-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="42f02-108">Tableau contenant 2 tuples</span><span class="sxs-lookup"><span data-stu-id="42f02-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="42f02-109">Sortie : ('t [], 'U [])</span><span class="sxs-lookup"><span data-stu-id="42f02-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="42f02-110">Deux tableaux, le premier contenant tous les premiers éléments des tuples d’entrée, le second contenant tous les secondes des tuples d’entrée.</span><span class="sxs-lookup"><span data-stu-id="42f02-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="42f02-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="42f02-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42f02-112">Peut</span><span class="sxs-lookup"><span data-stu-id="42f02-112">'T</span></span>

<span data-ttu-id="42f02-113">Type du premier élément de chaque tuple</span><span class="sxs-lookup"><span data-stu-id="42f02-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="42f02-114">'U</span><span class="sxs-lookup"><span data-stu-id="42f02-114">'U</span></span>

<span data-ttu-id="42f02-115">Type du deuxième élément de chaque tuple</span><span class="sxs-lookup"><span data-stu-id="42f02-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="42f02-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="42f02-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="42f02-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="42f02-117">See Also</span></span>

- [<span data-ttu-id="42f02-118">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="42f02-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)