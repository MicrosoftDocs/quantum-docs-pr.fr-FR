---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fonction inversée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845453"
---
# <a name="reversed-function"></a><span data-ttu-id="82313-102">Fonction inversée</span><span class="sxs-lookup"><span data-stu-id="82313-102">Reversed function</span></span>

<span data-ttu-id="82313-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="82313-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="82313-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="82313-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="82313-105">Créez un tableau qui contient les mêmes éléments qu’un tableau d’entrée, mais dans l’ordre inverse.</span><span class="sxs-lookup"><span data-stu-id="82313-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="82313-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="82313-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="82313-107">Tableau : 't []</span><span class="sxs-lookup"><span data-stu-id="82313-107">array : 'T[]</span></span>

<span data-ttu-id="82313-108">Tableau dont les éléments doivent être copiés dans l’ordre inverse.</span><span class="sxs-lookup"><span data-stu-id="82313-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="82313-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="82313-109">Output : 'T[]</span></span>

<span data-ttu-id="82313-110">Tableau contenant les éléments `array[Length(array) - 1]` ..</span><span class="sxs-lookup"><span data-stu-id="82313-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="82313-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="82313-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="82313-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="82313-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="82313-113">Peut</span><span class="sxs-lookup"><span data-stu-id="82313-113">'T</span></span>

<span data-ttu-id="82313-114">Type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="82313-114">The type of the array elements.</span></span>