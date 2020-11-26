---
uid: Microsoft.Quantum.Arrays.Tail
title: fonction Tail
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220091"
---
# <a name="tail-function"></a><span data-ttu-id="3de0b-102">fonction Tail</span><span class="sxs-lookup"><span data-stu-id="3de0b-102">Tail function</span></span>

<span data-ttu-id="3de0b-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3de0b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3de0b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3de0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3de0b-105">Retourne le dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="3de0b-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="3de0b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3de0b-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="3de0b-107">Tableau : 'A []</span><span class="sxs-lookup"><span data-stu-id="3de0b-107">array : 'A[]</span></span>

<span data-ttu-id="3de0b-108">Tableau dont le dernier élément est pris.</span><span class="sxs-lookup"><span data-stu-id="3de0b-108">Array of which the last element is taken.</span></span> <span data-ttu-id="3de0b-109">La longueur du tableau doit être au moins égale à 1.</span><span class="sxs-lookup"><span data-stu-id="3de0b-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="3de0b-110">Sortie : 'A</span><span class="sxs-lookup"><span data-stu-id="3de0b-110">Output : 'A</span></span>

<span data-ttu-id="3de0b-111">Dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="3de0b-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3de0b-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="3de0b-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="3de0b-113">'A</span><span class="sxs-lookup"><span data-stu-id="3de0b-113">'A</span></span>

<span data-ttu-id="3de0b-114">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="3de0b-114">The type of the array elements.</span></span>