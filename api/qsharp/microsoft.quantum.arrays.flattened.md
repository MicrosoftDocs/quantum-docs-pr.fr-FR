---
uid: Microsoft.Quantum.Arrays.Flattened
title: Fonction aplatie
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221213"
---
# <a name="flattened-function"></a><span data-ttu-id="d6666-102">Fonction aplatie</span><span class="sxs-lookup"><span data-stu-id="d6666-102">Flattened function</span></span>

<span data-ttu-id="d6666-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d6666-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d6666-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6666-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6666-105">À partir d’un tableau de tableaux, retourne la concaténation de tous les tableaux.</span><span class="sxs-lookup"><span data-stu-id="d6666-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d6666-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d6666-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="d6666-107">tableaux : 't [] []</span><span class="sxs-lookup"><span data-stu-id="d6666-107">arrays : 'T[][]</span></span>

<span data-ttu-id="d6666-108">Tableau de tableaux.</span><span class="sxs-lookup"><span data-stu-id="d6666-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="d6666-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="d6666-109">Output : 'T[]</span></span>

<span data-ttu-id="d6666-110">Concaténation de tous les tableaux.</span><span class="sxs-lookup"><span data-stu-id="d6666-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d6666-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d6666-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d6666-112">Peut</span><span class="sxs-lookup"><span data-stu-id="d6666-112">'T</span></span>

<span data-ttu-id="d6666-113">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="d6666-113">The type of `array` elements.</span></span>