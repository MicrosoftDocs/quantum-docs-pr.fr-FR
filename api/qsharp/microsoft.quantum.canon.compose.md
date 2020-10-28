---
uid: Microsoft.Quantum.Canon.Compose
title: Compose, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704355"
---
# <a name="compose-function"></a><span data-ttu-id="1317b-102">Compose, fonction</span><span class="sxs-lookup"><span data-stu-id="1317b-102">Compose function</span></span>

<span data-ttu-id="1317b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1317b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1317b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1317b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1317b-105">Retourne la composition de deux fonctions.</span><span class="sxs-lookup"><span data-stu-id="1317b-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="1317b-106">Description</span><span class="sxs-lookup"><span data-stu-id="1317b-106">Description</span></span>

<span data-ttu-id="1317b-107">À partir de deux fonctions $f $ et $g $, retourne une nouvelle fonction représentant $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="1317b-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="1317b-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="1317b-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="1317b-109">externe : 'U-> 'V</span><span class="sxs-lookup"><span data-stu-id="1317b-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="1317b-110">Deuxième fonction à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1317b-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="1317b-111">interne : t-> 'U</span><span class="sxs-lookup"><span data-stu-id="1317b-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="1317b-112">Première fonction à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1317b-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="1317b-113">Sortie : 't-> 'V</span><span class="sxs-lookup"><span data-stu-id="1317b-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="1317b-114">Une nouvelle fonction $h $ de telle sorte que toutes les entrées $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="1317b-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1317b-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1317b-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1317b-116">Peut</span><span class="sxs-lookup"><span data-stu-id="1317b-116">'T</span></span>

<span data-ttu-id="1317b-117">Type d’entrée de la première fonction à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1317b-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="1317b-118">'U</span><span class="sxs-lookup"><span data-stu-id="1317b-118">'U</span></span>

<span data-ttu-id="1317b-119">Type de sortie de la première fonction à appliquer et type d’entrée de la deuxième fonction à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1317b-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="1317b-120">'V</span><span class="sxs-lookup"><span data-stu-id="1317b-120">'V</span></span>

<span data-ttu-id="1317b-121">Type de sortie de la deuxième fonction à appliquer.</span><span class="sxs-lookup"><span data-stu-id="1317b-121">The output type of the second function to be applied.</span></span>