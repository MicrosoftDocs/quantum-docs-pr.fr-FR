---
uid: Microsoft.Quantum.Arrays.Most
title: La plupart des fonctions
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705862"
---
# <a name="most-function"></a><span data-ttu-id="221ec-102">La plupart des fonctions</span><span class="sxs-lookup"><span data-stu-id="221ec-102">Most function</span></span>

<span data-ttu-id="221ec-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="221ec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="221ec-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="221ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="221ec-105">Crée un tableau qui est égal à un tableau d’entrée, sauf que le dernier élément de tableau est supprimé.</span><span class="sxs-lookup"><span data-stu-id="221ec-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="221ec-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="221ec-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="221ec-107">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="221ec-107">array : 'T[]</span></span>

<span data-ttu-id="221ec-108">Tableau dont le premier à l’avant-dernier élément doit former le tableau de sortie.</span><span class="sxs-lookup"><span data-stu-id="221ec-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="221ec-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="221ec-109">Output : 'T[]</span></span>

<span data-ttu-id="221ec-110">Tableau contenant les éléments `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="221ec-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="221ec-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="221ec-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="221ec-112">Peut</span><span class="sxs-lookup"><span data-stu-id="221ec-112">'T</span></span>

<span data-ttu-id="221ec-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="221ec-113">The type of the array elements.</span></span>