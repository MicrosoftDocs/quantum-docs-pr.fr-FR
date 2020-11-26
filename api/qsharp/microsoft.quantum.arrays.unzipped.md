---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Fonction unzippée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219955"
---
# <a name="unzipped-function"></a><span data-ttu-id="2e79d-102">Fonction unzippée</span><span class="sxs-lookup"><span data-stu-id="2e79d-102">Unzipped function</span></span>

<span data-ttu-id="2e79d-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2e79d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2e79d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e79d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e79d-105">À partir d’un tableau de 2 tuples, retourne un tuple de deux tableaux, chacun contenant les éléments des tuples du tableau d’entrée.</span><span class="sxs-lookup"><span data-stu-id="2e79d-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="2e79d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2e79d-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="2e79d-107">ARR : ('t, 'U) []</span><span class="sxs-lookup"><span data-stu-id="2e79d-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="2e79d-108">Tableau contenant 2 tuples</span><span class="sxs-lookup"><span data-stu-id="2e79d-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="2e79d-109">Sortie : ('t [], 'U [])</span><span class="sxs-lookup"><span data-stu-id="2e79d-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="2e79d-110">Deux tableaux, le premier contenant tous les premiers éléments des tuples d’entrée, le second contenant tous les secondes des tuples d’entrée.</span><span class="sxs-lookup"><span data-stu-id="2e79d-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2e79d-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2e79d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e79d-112">Peut</span><span class="sxs-lookup"><span data-stu-id="2e79d-112">'T</span></span>

<span data-ttu-id="2e79d-113">Type du premier élément de chaque tuple</span><span class="sxs-lookup"><span data-stu-id="2e79d-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="2e79d-114">'U</span><span class="sxs-lookup"><span data-stu-id="2e79d-114">'U</span></span>

<span data-ttu-id="2e79d-115">Type du deuxième élément de chaque tuple</span><span class="sxs-lookup"><span data-stu-id="2e79d-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="2e79d-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e79d-116">See Also</span></span>

- [<span data-ttu-id="2e79d-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="2e79d-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)