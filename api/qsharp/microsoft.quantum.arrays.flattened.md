---
uid: Microsoft.Quantum.Arrays.Flattened
title: Fonction aplatie
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848614"
---
# <a name="flattened-function"></a><span data-ttu-id="0e65a-102">Fonction aplatie</span><span class="sxs-lookup"><span data-stu-id="0e65a-102">Flattened function</span></span>

<span data-ttu-id="0e65a-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0e65a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0e65a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e65a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e65a-105">À partir d’un tableau de tableaux, retourne la concaténation de tous les tableaux.</span><span class="sxs-lookup"><span data-stu-id="0e65a-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0e65a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0e65a-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="0e65a-107">tableaux : 't [] []</span><span class="sxs-lookup"><span data-stu-id="0e65a-107">arrays : 'T[][]</span></span>

<span data-ttu-id="0e65a-108">Tableau de tableaux.</span><span class="sxs-lookup"><span data-stu-id="0e65a-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="0e65a-109">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="0e65a-109">Output : 'T[]</span></span>

<span data-ttu-id="0e65a-110">Concaténation de tous les tableaux.</span><span class="sxs-lookup"><span data-stu-id="0e65a-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0e65a-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0e65a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e65a-112">Peut</span><span class="sxs-lookup"><span data-stu-id="0e65a-112">'T</span></span>

<span data-ttu-id="0e65a-113">Type des `array` éléments.</span><span class="sxs-lookup"><span data-stu-id="0e65a-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="0e65a-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="0e65a-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```