---
uid: Microsoft.Quantum.Arrays.Most
title: La plupart des fonctions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845577"
---
# <a name="most-function"></a><span data-ttu-id="95b19-102">La plupart des fonctions</span><span class="sxs-lookup"><span data-stu-id="95b19-102">Most function</span></span>

<span data-ttu-id="95b19-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="95b19-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="95b19-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95b19-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95b19-105">Crée un tableau qui est égal à un tableau d’entrée, sauf que le dernier élément de tableau est supprimé.</span><span class="sxs-lookup"><span data-stu-id="95b19-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="95b19-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="95b19-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="95b19-107">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="95b19-107">array : 'T[]</span></span>

<span data-ttu-id="95b19-108">Tableau dont le premier à l’avant-dernier élément doit former le tableau de sortie.</span><span class="sxs-lookup"><span data-stu-id="95b19-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="95b19-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="95b19-109">Output : 'T[]</span></span>

<span data-ttu-id="95b19-110">Tableau contenant les éléments `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="95b19-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="95b19-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="95b19-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95b19-112">Peut</span><span class="sxs-lookup"><span data-stu-id="95b19-112">'T</span></span>

<span data-ttu-id="95b19-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="95b19-113">The type of the array elements.</span></span>