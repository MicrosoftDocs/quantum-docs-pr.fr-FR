---
uid: Microsoft.Quantum.Arrays.Rest
title: Fonction Rest
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705806"
---
# <a name="rest-function"></a><span data-ttu-id="7614a-102">Fonction Rest</span><span class="sxs-lookup"><span data-stu-id="7614a-102">Rest function</span></span>

<span data-ttu-id="7614a-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7614a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7614a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7614a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7614a-105">Crée un tableau qui est égal à un tableau d’entrée, sauf que le premier élément de tableau est supprimé.</span><span class="sxs-lookup"><span data-stu-id="7614a-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7614a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7614a-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="7614a-107">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="7614a-107">array : 'T[]</span></span>

<span data-ttu-id="7614a-108">Tableau dont l’avant-dernier élément doit former le tableau de sortie.</span><span class="sxs-lookup"><span data-stu-id="7614a-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="7614a-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="7614a-109">Output : 'T[]</span></span>

<span data-ttu-id="7614a-110">Tableau contenant les éléments `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="7614a-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7614a-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="7614a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7614a-112">Peut</span><span class="sxs-lookup"><span data-stu-id="7614a-112">'T</span></span>

<span data-ttu-id="7614a-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="7614a-113">The type of the array elements.</span></span>