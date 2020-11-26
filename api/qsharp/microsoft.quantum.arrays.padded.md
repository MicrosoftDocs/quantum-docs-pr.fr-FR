---
uid: Microsoft.Quantum.Arrays.Padded
title: Fonction rembourrée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220533"
---
# <a name="padded-function"></a><span data-ttu-id="fe2cb-102">Fonction rembourrée</span><span class="sxs-lookup"><span data-stu-id="fe2cb-102">Padded function</span></span>

<span data-ttu-id="fe2cb-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fe2cb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fe2cb-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe2cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe2cb-105">Retourne un tableau rempli à l’aide des valeurs spécifiées jusqu’à une longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="fe2cb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fe2cb-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="fe2cb-107">nElementsTotal : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fe2cb-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fe2cb-108">Longueur du tableau rempli.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-108">The length of the padded array.</span></span> <span data-ttu-id="fe2cb-109">Si ce est positif, `inputArray` est rempli à l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="fe2cb-110">Si ce est négatif, `inputArray` est rempli à la fin.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="fe2cb-111">defaultElement : 't</span><span class="sxs-lookup"><span data-stu-id="fe2cb-111">defaultElement : 'T</span></span>

<span data-ttu-id="fe2cb-112">Valeur par défaut à utiliser pour les éléments de remplissage.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="fe2cb-113">inputArray : 't []</span><span class="sxs-lookup"><span data-stu-id="fe2cb-113">inputArray : 'T[]</span></span>

<span data-ttu-id="fe2cb-114">Tableau dont les valeurs sont situées à l’en-tête du tableau de sortie.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="fe2cb-115">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="fe2cb-115">Output : 'T[]</span></span>

<span data-ttu-id="fe2cb-116">Tableau `output` qui est le `inputArray` remplissage de l’en-tête avec `defaultElement` s jusqu’à ce que `output` ait une longueur `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="fe2cb-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fe2cb-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="fe2cb-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe2cb-118">Peut</span><span class="sxs-lookup"><span data-stu-id="fe2cb-118">'T</span></span>

<span data-ttu-id="fe2cb-119">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="fe2cb-119">The type of the array elements.</span></span>