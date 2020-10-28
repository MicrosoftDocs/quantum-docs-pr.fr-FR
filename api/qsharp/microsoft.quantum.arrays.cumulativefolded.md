---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706126"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="7eec5-102">CumulativeFolded fonction)</span><span class="sxs-lookup"><span data-stu-id="7eec5-102">CumulativeFolded function</span></span>

<span data-ttu-id="7eec5-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7eec5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7eec5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7eec5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7eec5-105">Combine mappé et pli dans une fonction unique</span><span class="sxs-lookup"><span data-stu-id="7eec5-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="7eec5-106">Description</span><span class="sxs-lookup"><span data-stu-id="7eec5-106">Description</span></span>

<span data-ttu-id="7eec5-107">Cette fonction itère la `fn` fonction via le tableau, en commençant à un état initial `state` et retourne toutes les valeurs intermédiaires, à l’exclusion de l’état initial.</span><span class="sxs-lookup"><span data-stu-id="7eec5-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="7eec5-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="7eec5-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="7eec5-109">FN : ('State, t)-> 'State</span><span class="sxs-lookup"><span data-stu-id="7eec5-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="7eec5-110">Fonction à replier sur le tableau</span><span class="sxs-lookup"><span data-stu-id="7eec5-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="7eec5-111">État : 'État</span><span class="sxs-lookup"><span data-stu-id="7eec5-111">state : 'State</span></span>

<span data-ttu-id="7eec5-112">État initial à replier</span><span class="sxs-lookup"><span data-stu-id="7eec5-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="7eec5-113">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="7eec5-113">array : 'T[]</span></span>

<span data-ttu-id="7eec5-114">Tableau de valeurs à replier</span><span class="sxs-lookup"><span data-stu-id="7eec5-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="7eec5-115">Sortie : 'State []</span><span class="sxs-lookup"><span data-stu-id="7eec5-115">Output : 'State[]</span></span>

<span data-ttu-id="7eec5-116">Tous les États intermédiaires, y compris l’état final, mais pas l’état initial.</span><span class="sxs-lookup"><span data-stu-id="7eec5-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="7eec5-117">La longueur du tableau de sortie est de la même longueur que `array` .</span><span class="sxs-lookup"><span data-stu-id="7eec5-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7eec5-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7eec5-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="7eec5-119">'État</span><span class="sxs-lookup"><span data-stu-id="7eec5-119">'State</span></span>

<span data-ttu-id="7eec5-120">Le type d’État sur lequel la `fn` fonction opère, par exemple, accepte comme première entrée et retourne.</span><span class="sxs-lookup"><span data-stu-id="7eec5-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="7eec5-121">Peut</span><span class="sxs-lookup"><span data-stu-id="7eec5-121">'T</span></span>

<span data-ttu-id="7eec5-122">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="7eec5-122">The type of `array` elements.</span></span>