---
uid: Microsoft.Quantum.Arrays.Tail
title: fonction Tail
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705742"
---
# <a name="tail-function"></a><span data-ttu-id="732e5-102">fonction Tail</span><span class="sxs-lookup"><span data-stu-id="732e5-102">Tail function</span></span>

<span data-ttu-id="732e5-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="732e5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="732e5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="732e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="732e5-105">Retourne le dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="732e5-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="732e5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="732e5-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="732e5-107">Tableau : 'A []</span><span class="sxs-lookup"><span data-stu-id="732e5-107">array : 'A[]</span></span>

<span data-ttu-id="732e5-108">Tableau dont le dernier élément est pris.</span><span class="sxs-lookup"><span data-stu-id="732e5-108">Array of which the last element is taken.</span></span> <span data-ttu-id="732e5-109">La longueur du tableau doit être au moins égale à 1.</span><span class="sxs-lookup"><span data-stu-id="732e5-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="732e5-110">Sortie : 'A</span><span class="sxs-lookup"><span data-stu-id="732e5-110">Output : 'A</span></span>

<span data-ttu-id="732e5-111">Dernier élément du tableau.</span><span class="sxs-lookup"><span data-stu-id="732e5-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="732e5-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="732e5-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="732e5-113">'A</span><span class="sxs-lookup"><span data-stu-id="732e5-113">'A</span></span>

<span data-ttu-id="732e5-114">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="732e5-114">The type of the array elements.</span></span>