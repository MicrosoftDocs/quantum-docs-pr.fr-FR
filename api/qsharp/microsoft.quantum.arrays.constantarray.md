---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210061"
---
# <a name="constantarray-function"></a><span data-ttu-id="ad3fc-102">ConstantArray fonction)</span><span class="sxs-lookup"><span data-stu-id="ad3fc-102">ConstantArray function</span></span>

<span data-ttu-id="ad3fc-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ad3fc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ad3fc-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad3fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad3fc-105">Crée un tableau de longueur donnée avec tous les éléments égaux à la valeur donnée.</span><span class="sxs-lookup"><span data-stu-id="ad3fc-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ad3fc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ad3fc-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="ad3fc-107">Longueur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad3fc-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad3fc-108">Longueur du nouveau tableau.</span><span class="sxs-lookup"><span data-stu-id="ad3fc-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="ad3fc-109">valeur : 't</span><span class="sxs-lookup"><span data-stu-id="ad3fc-109">value : 'T</span></span>

<span data-ttu-id="ad3fc-110">Valeur de chaque élément du nouveau tableau.</span><span class="sxs-lookup"><span data-stu-id="ad3fc-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="ad3fc-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="ad3fc-111">Output : 'T[]</span></span>

<span data-ttu-id="ad3fc-112">Nouveau tableau de longueur `length` , de telle sorte que chaque élément est `value` .</span><span class="sxs-lookup"><span data-stu-id="ad3fc-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ad3fc-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ad3fc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad3fc-114">Peut</span><span class="sxs-lookup"><span data-stu-id="ad3fc-114">'T</span></span>

