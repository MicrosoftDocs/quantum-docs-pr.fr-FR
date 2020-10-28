---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fonction inversée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705803"
---
# <a name="reversed-function"></a><span data-ttu-id="a9b80-102">Fonction inversée</span><span class="sxs-lookup"><span data-stu-id="a9b80-102">Reversed function</span></span>

<span data-ttu-id="a9b80-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a9b80-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a9b80-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9b80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9b80-105">Créez un tableau qui contient les mêmes éléments qu’un tableau d’entrée, mais dans l’ordre inverse.</span><span class="sxs-lookup"><span data-stu-id="a9b80-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a9b80-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a9b80-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="a9b80-107">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="a9b80-107">array : 'T[]</span></span>

<span data-ttu-id="a9b80-108">Tableau dont les éléments doivent être copiés dans l’ordre inverse.</span><span class="sxs-lookup"><span data-stu-id="a9b80-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="a9b80-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="a9b80-109">Output : 'T[]</span></span>

<span data-ttu-id="a9b80-110">Tableau contenant les éléments `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="a9b80-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="a9b80-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="a9b80-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a9b80-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a9b80-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9b80-113">Peut</span><span class="sxs-lookup"><span data-stu-id="a9b80-113">'T</span></span>

<span data-ttu-id="a9b80-114">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="a9b80-114">The type of the array elements.</span></span>