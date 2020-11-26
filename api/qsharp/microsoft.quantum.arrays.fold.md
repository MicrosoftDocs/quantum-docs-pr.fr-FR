---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221162"
---
# <a name="fold-function"></a><span data-ttu-id="76b3d-102">Fold, fonction</span><span class="sxs-lookup"><span data-stu-id="76b3d-102">Fold function</span></span>

<span data-ttu-id="76b3d-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="76b3d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="76b3d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76b3d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76b3d-105">Itère une fonction `f` via un tableau `array` , en retournant `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="76b3d-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="76b3d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="76b3d-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="76b3d-107">dossier : (« État, t)-> » État</span><span class="sxs-lookup"><span data-stu-id="76b3d-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="76b3d-108">Fonction à plier sur le tableau.</span><span class="sxs-lookup"><span data-stu-id="76b3d-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="76b3d-109">État : 'État</span><span class="sxs-lookup"><span data-stu-id="76b3d-109">state : 'State</span></span>

<span data-ttu-id="76b3d-110">État initial du dossier.</span><span class="sxs-lookup"><span data-stu-id="76b3d-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="76b3d-111">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="76b3d-111">array : 'T[]</span></span>

<span data-ttu-id="76b3d-112">Tableau de valeurs à replier.</span><span class="sxs-lookup"><span data-stu-id="76b3d-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="76b3d-113">Sortie : 'State</span><span class="sxs-lookup"><span data-stu-id="76b3d-113">Output : 'State</span></span>

<span data-ttu-id="76b3d-114">État final retourné par le dossier après l’itération sur tous les éléments de `array` .</span><span class="sxs-lookup"><span data-stu-id="76b3d-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="76b3d-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="76b3d-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="76b3d-116">'État</span><span class="sxs-lookup"><span data-stu-id="76b3d-116">'State</span></span>

<span data-ttu-id="76b3d-117">Le type d’État sur lequel la `folder` fonction opère, par exemple, accepte comme premier argument et retourne.</span><span class="sxs-lookup"><span data-stu-id="76b3d-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="76b3d-118">Peut</span><span class="sxs-lookup"><span data-stu-id="76b3d-118">'T</span></span>

<span data-ttu-id="76b3d-119">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="76b3d-119">The type of `array` elements.</span></span>