---
uid: Microsoft.Quantum.Arrays.Flattened
title: Fonction aplatie
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706022"
---
# <a name="flattened-function"></a><span data-ttu-id="e4450-102">Fonction aplatie</span><span class="sxs-lookup"><span data-stu-id="e4450-102">Flattened function</span></span>

<span data-ttu-id="e4450-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e4450-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e4450-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4450-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4450-105">À partir d’un tableau de tableaux, retourne la concaténation de tous les tableaux.</span><span class="sxs-lookup"><span data-stu-id="e4450-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e4450-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e4450-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="e4450-107">tableaux : 't [] []</span><span class="sxs-lookup"><span data-stu-id="e4450-107">arrays : 'T[][]</span></span>

<span data-ttu-id="e4450-108">Tableau de tableaux.</span><span class="sxs-lookup"><span data-stu-id="e4450-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="e4450-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="e4450-109">Output : 'T[]</span></span>

<span data-ttu-id="e4450-110">Concaténation de tous les tableaux.</span><span class="sxs-lookup"><span data-stu-id="e4450-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e4450-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e4450-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4450-112">Peut</span><span class="sxs-lookup"><span data-stu-id="e4450-112">'T</span></span>

<span data-ttu-id="e4450-113">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="e4450-113">The type of `array` elements.</span></span>