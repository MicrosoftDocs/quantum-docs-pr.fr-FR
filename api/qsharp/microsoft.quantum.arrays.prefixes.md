---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Fonction Prefixes
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220384"
---
# <a name="prefixes-function"></a><span data-ttu-id="9a4cf-102">Fonction Prefixes</span><span class="sxs-lookup"><span data-stu-id="9a4cf-102">Prefixes function</span></span>

<span data-ttu-id="9a4cf-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9a4cf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9a4cf-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a4cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a4cf-105">À partir d’un tableau, retourne tous ses préfixes.</span><span class="sxs-lookup"><span data-stu-id="9a4cf-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="9a4cf-106">Description</span><span class="sxs-lookup"><span data-stu-id="9a4cf-106">Description</span></span>

<span data-ttu-id="9a4cf-107">Retourne un tableau de tous les préfixes, en commençant par un tableau qui a uniquement le premier élément jusqu’au tableau complet.</span><span class="sxs-lookup"><span data-stu-id="9a4cf-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="9a4cf-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="9a4cf-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="9a4cf-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="9a4cf-109">array : 'T[]</span></span>

<span data-ttu-id="9a4cf-110">Tableau d’éléments.</span><span class="sxs-lookup"><span data-stu-id="9a4cf-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="9a4cf-111">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="9a4cf-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a4cf-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9a4cf-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a4cf-113">Peut</span><span class="sxs-lookup"><span data-stu-id="9a4cf-113">'T</span></span>

<span data-ttu-id="9a4cf-114">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="9a4cf-114">The type of `array` elements.</span></span>