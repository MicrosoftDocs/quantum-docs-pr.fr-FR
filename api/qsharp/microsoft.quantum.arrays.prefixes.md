---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Fonction Prefixes
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845508"
---
# <a name="prefixes-function"></a><span data-ttu-id="fe5ec-102">Fonction Prefixes</span><span class="sxs-lookup"><span data-stu-id="fe5ec-102">Prefixes function</span></span>

<span data-ttu-id="fe5ec-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fe5ec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fe5ec-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe5ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe5ec-105">À partir d’un tableau, retourne tous ses préfixes.</span><span class="sxs-lookup"><span data-stu-id="fe5ec-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="fe5ec-106">Description</span><span class="sxs-lookup"><span data-stu-id="fe5ec-106">Description</span></span>

<span data-ttu-id="fe5ec-107">Retourne un tableau de tous les préfixes, en commençant par un tableau qui a uniquement le premier élément jusqu’au tableau complet.</span><span class="sxs-lookup"><span data-stu-id="fe5ec-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="fe5ec-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="fe5ec-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="fe5ec-109">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="fe5ec-109">array : 'T[]</span></span>

<span data-ttu-id="fe5ec-110">Tableau d’éléments.</span><span class="sxs-lookup"><span data-stu-id="fe5ec-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="fe5ec-111">Sortie : 't [] []</span><span class="sxs-lookup"><span data-stu-id="fe5ec-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fe5ec-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="fe5ec-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe5ec-113">Peut</span><span class="sxs-lookup"><span data-stu-id="fe5ec-113">'T</span></span>

<span data-ttu-id="fe5ec-114">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="fe5ec-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="fe5ec-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="fe5ec-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```