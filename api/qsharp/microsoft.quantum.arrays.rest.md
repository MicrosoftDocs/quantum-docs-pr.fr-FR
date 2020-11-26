---
uid: Microsoft.Quantum.Arrays.Rest
title: Fonction Rest
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220386"
---
# <a name="rest-function"></a><span data-ttu-id="bd741-102">Fonction Rest</span><span class="sxs-lookup"><span data-stu-id="bd741-102">Rest function</span></span>

<span data-ttu-id="bd741-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bd741-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bd741-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd741-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd741-105">Crée un tableau qui est égal à un tableau d’entrée, sauf que le premier élément de tableau est supprimé.</span><span class="sxs-lookup"><span data-stu-id="bd741-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bd741-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="bd741-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bd741-107">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="bd741-107">array : 'T[]</span></span>

<span data-ttu-id="bd741-108">Tableau dont l’avant-dernier élément doit former le tableau de sortie.</span><span class="sxs-lookup"><span data-stu-id="bd741-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="bd741-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="bd741-109">Output : 'T[]</span></span>

<span data-ttu-id="bd741-110">Tableau contenant les éléments `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="bd741-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd741-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="bd741-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd741-112">Peut</span><span class="sxs-lookup"><span data-stu-id="bd741-112">'T</span></span>

<span data-ttu-id="bd741-113">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="bd741-113">The type of the array elements.</span></span>