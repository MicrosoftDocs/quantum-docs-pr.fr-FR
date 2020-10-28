---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Fonction unzippée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705723"
---
# <a name="unzipped-function"></a><span data-ttu-id="cf767-102">Fonction unzippée</span><span class="sxs-lookup"><span data-stu-id="cf767-102">Unzipped function</span></span>

<span data-ttu-id="cf767-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cf767-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cf767-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf767-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf767-105">À partir d’un tableau de 2 tuples, retourne un tuple de deux tableaux, chacun contenant les éléments des tuples du tableau d’entrée.</span><span class="sxs-lookup"><span data-stu-id="cf767-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="cf767-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="cf767-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="cf767-107">ARR : ('t, 'U) []</span><span class="sxs-lookup"><span data-stu-id="cf767-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="cf767-108">Tableau contenant 2 tuples</span><span class="sxs-lookup"><span data-stu-id="cf767-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="cf767-109">Sortie : ('t [], 'U [])</span><span class="sxs-lookup"><span data-stu-id="cf767-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="cf767-110">Deux tableaux, le premier contenant tous les premiers éléments des tuples d’entrée, le second contenant tous les secondes des tuples d’entrée.</span><span class="sxs-lookup"><span data-stu-id="cf767-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cf767-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="cf767-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cf767-112">Peut</span><span class="sxs-lookup"><span data-stu-id="cf767-112">'T</span></span>

<span data-ttu-id="cf767-113">Type du premier élément de chaque tuple</span><span class="sxs-lookup"><span data-stu-id="cf767-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="cf767-114">'U</span><span class="sxs-lookup"><span data-stu-id="cf767-114">'U</span></span>

<span data-ttu-id="cf767-115">Type du deuxième élément de chaque tuple</span><span class="sxs-lookup"><span data-stu-id="cf767-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="cf767-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf767-116">See Also</span></span>

- [<span data-ttu-id="cf767-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="cf767-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)