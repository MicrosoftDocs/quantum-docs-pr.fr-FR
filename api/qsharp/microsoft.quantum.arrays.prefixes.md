---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Fonction Prefixes
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705822"
---
# <a name="prefixes-function"></a><span data-ttu-id="48fce-102">Fonction Prefixes</span><span class="sxs-lookup"><span data-stu-id="48fce-102">Prefixes function</span></span>

<span data-ttu-id="48fce-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="48fce-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="48fce-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48fce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48fce-105">À partir d’un tableau, retourne tous ses préfixes.</span><span class="sxs-lookup"><span data-stu-id="48fce-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="48fce-106">Description</span><span class="sxs-lookup"><span data-stu-id="48fce-106">Description</span></span>

<span data-ttu-id="48fce-107">Retourne un tableau de tous les préfixes, en commençant par un tableau qui a uniquement le premier élément jusqu’au tableau complet.</span><span class="sxs-lookup"><span data-stu-id="48fce-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="48fce-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="48fce-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="48fce-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="48fce-109">array : 'T[]</span></span>

<span data-ttu-id="48fce-110">Tableau d’éléments.</span><span class="sxs-lookup"><span data-stu-id="48fce-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="48fce-111">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="48fce-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="48fce-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="48fce-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48fce-113">Peut</span><span class="sxs-lookup"><span data-stu-id="48fce-113">'T</span></span>

<span data-ttu-id="48fce-114">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="48fce-114">The type of `array` elements.</span></span>