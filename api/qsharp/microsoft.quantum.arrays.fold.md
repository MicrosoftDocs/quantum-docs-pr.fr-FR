---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848604"
---
# <a name="fold-function"></a><span data-ttu-id="a228a-102">Fold, fonction</span><span class="sxs-lookup"><span data-stu-id="a228a-102">Fold function</span></span>

<span data-ttu-id="a228a-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a228a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a228a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a228a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a228a-105">Itère une fonction `f` via un tableau `array` , en retournant `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="a228a-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="a228a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a228a-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="a228a-107">dossier : (« État, t)-> » État</span><span class="sxs-lookup"><span data-stu-id="a228a-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="a228a-108">Fonction à plier sur le tableau.</span><span class="sxs-lookup"><span data-stu-id="a228a-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="a228a-109">État : 'État</span><span class="sxs-lookup"><span data-stu-id="a228a-109">state : 'State</span></span>

<span data-ttu-id="a228a-110">État initial du dossier.</span><span class="sxs-lookup"><span data-stu-id="a228a-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="a228a-111">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="a228a-111">array : 'T[]</span></span>

<span data-ttu-id="a228a-112">Tableau de valeurs à replier.</span><span class="sxs-lookup"><span data-stu-id="a228a-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="a228a-113">Sortie : 'State</span><span class="sxs-lookup"><span data-stu-id="a228a-113">Output : 'State</span></span>

<span data-ttu-id="a228a-114">État final retourné par le dossier après l’itération sur tous les éléments de `array` .</span><span class="sxs-lookup"><span data-stu-id="a228a-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a228a-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a228a-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="a228a-116">'État</span><span class="sxs-lookup"><span data-stu-id="a228a-116">'State</span></span>

<span data-ttu-id="a228a-117">Le type d’État sur lequel la `folder` fonction opère, par exemple, accepte comme premier argument et retourne.</span><span class="sxs-lookup"><span data-stu-id="a228a-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="a228a-118">Peut</span><span class="sxs-lookup"><span data-stu-id="a228a-118">'T</span></span>

<span data-ttu-id="a228a-119">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="a228a-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="a228a-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="a228a-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```