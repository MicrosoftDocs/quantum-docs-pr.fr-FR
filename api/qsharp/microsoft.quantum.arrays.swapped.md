---
uid: Microsoft.Quantum.Arrays.Swapped
title: Permuted, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850948"
---
# <a name="swapped-function"></a><span data-ttu-id="abc24-102">Permuted, fonction</span><span class="sxs-lookup"><span data-stu-id="abc24-102">Swapped function</span></span>

<span data-ttu-id="abc24-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="abc24-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="abc24-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abc24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="abc24-105">Applique un échange de deux éléments dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="abc24-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="abc24-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="abc24-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="abc24-107">firstIndex : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abc24-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abc24-108">Index du premier élément à permuter.</span><span class="sxs-lookup"><span data-stu-id="abc24-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="abc24-109">secondIndex : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abc24-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abc24-110">Index du deuxième élément à permuter.</span><span class="sxs-lookup"><span data-stu-id="abc24-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="abc24-111">ARR : 't []</span><span class="sxs-lookup"><span data-stu-id="abc24-111">arr : 'T[]</span></span>

<span data-ttu-id="abc24-112">Tableau contenant les éléments à permuter.</span><span class="sxs-lookup"><span data-stu-id="abc24-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="abc24-113">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="abc24-113">Output : 'T[]</span></span>

<span data-ttu-id="abc24-114">Tableau avec l’échange sur place appliqué.</span><span class="sxs-lookup"><span data-stu-id="abc24-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="abc24-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="abc24-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="abc24-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="abc24-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="abc24-117">Peut</span><span class="sxs-lookup"><span data-stu-id="abc24-117">'T</span></span>

