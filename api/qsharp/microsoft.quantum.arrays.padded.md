---
uid: Microsoft.Quantum.Arrays.Padded
title: Fonction rembourrée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845564"
---
# <a name="padded-function"></a><span data-ttu-id="3afee-102">Fonction rembourrée</span><span class="sxs-lookup"><span data-stu-id="3afee-102">Padded function</span></span>

<span data-ttu-id="3afee-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3afee-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3afee-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3afee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3afee-105">Retourne un tableau rempli à l’aide des valeurs spécifiées jusqu’à une longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="3afee-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3afee-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3afee-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="3afee-107">nElementsTotal : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3afee-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3afee-108">Longueur du tableau rempli.</span><span class="sxs-lookup"><span data-stu-id="3afee-108">The length of the padded array.</span></span> <span data-ttu-id="3afee-109">Si ce est positif, `inputArray` est rempli à l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="3afee-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="3afee-110">Si ce est négatif, `inputArray` est rempli à la fin.</span><span class="sxs-lookup"><span data-stu-id="3afee-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="3afee-111">defaultElement : 't</span><span class="sxs-lookup"><span data-stu-id="3afee-111">defaultElement : 'T</span></span>

<span data-ttu-id="3afee-112">Valeur par défaut à utiliser pour les éléments de remplissage.</span><span class="sxs-lookup"><span data-stu-id="3afee-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="3afee-113">inputArray : 't []</span><span class="sxs-lookup"><span data-stu-id="3afee-113">inputArray : 'T[]</span></span>

<span data-ttu-id="3afee-114">Tableau dont les valeurs sont situées à l’en-tête du tableau de sortie.</span><span class="sxs-lookup"><span data-stu-id="3afee-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="3afee-115">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="3afee-115">Output : 'T[]</span></span>

<span data-ttu-id="3afee-116">Tableau `output` qui est le `inputArray` remplissage de l’en-tête avec `defaultElement` s jusqu’à ce que `output` ait une longueur `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="3afee-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3afee-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="3afee-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3afee-118">Peut</span><span class="sxs-lookup"><span data-stu-id="3afee-118">'T</span></span>

<span data-ttu-id="3afee-119">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="3afee-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="3afee-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="3afee-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```