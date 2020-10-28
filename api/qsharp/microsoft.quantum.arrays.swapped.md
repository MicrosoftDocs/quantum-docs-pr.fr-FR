---
uid: Microsoft.Quantum.Arrays.Swapped
title: Permuted, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705747"
---
# <a name="swapped-function"></a><span data-ttu-id="50444-102">Permuted, fonction</span><span class="sxs-lookup"><span data-stu-id="50444-102">Swapped function</span></span>

<span data-ttu-id="50444-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50444-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50444-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50444-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50444-105">Applique un échange de deux éléments dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="50444-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="50444-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="50444-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="50444-107">firstIndex : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50444-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50444-108">Index du premier élément à permuter.</span><span class="sxs-lookup"><span data-stu-id="50444-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="50444-109">secondIndex : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50444-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50444-110">Index du deuxième élément à permuter.</span><span class="sxs-lookup"><span data-stu-id="50444-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="50444-111">ARR : 't []</span><span class="sxs-lookup"><span data-stu-id="50444-111">arr : 'T[]</span></span>

<span data-ttu-id="50444-112">Tableau contenant les éléments à permuter.</span><span class="sxs-lookup"><span data-stu-id="50444-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="50444-113">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="50444-113">Output : 'T[]</span></span>

<span data-ttu-id="50444-114">Tableau avec l’échange sur place appliqué.</span><span class="sxs-lookup"><span data-stu-id="50444-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="50444-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="50444-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="50444-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="50444-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50444-117">Peut</span><span class="sxs-lookup"><span data-stu-id="50444-117">'T</span></span>

