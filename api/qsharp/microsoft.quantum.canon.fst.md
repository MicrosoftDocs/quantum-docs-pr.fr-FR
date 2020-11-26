---
uid: Microsoft.Quantum.Canon.Fst
title: FST, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206933"
---
# <a name="fst-function"></a><span data-ttu-id="a20e3-102">FST, fonction</span><span class="sxs-lookup"><span data-stu-id="a20e3-102">Fst function</span></span>

<span data-ttu-id="a20e3-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a20e3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a20e3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a20e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a20e3-105">À partir d’une paire, retourne son premier élément.</span><span class="sxs-lookup"><span data-stu-id="a20e3-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="a20e3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a20e3-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="a20e3-107">paire : ('t, 'U)</span><span class="sxs-lookup"><span data-stu-id="a20e3-107">pair : ('T,'U)</span></span>

<span data-ttu-id="a20e3-108">Tuple avec deux éléments.</span><span class="sxs-lookup"><span data-stu-id="a20e3-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="a20e3-109">Sortie : 't</span><span class="sxs-lookup"><span data-stu-id="a20e3-109">Output : 'T</span></span>

<span data-ttu-id="a20e3-110">Premier élément de `pair`.</span><span class="sxs-lookup"><span data-stu-id="a20e3-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a20e3-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a20e3-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a20e3-112">Peut</span><span class="sxs-lookup"><span data-stu-id="a20e3-112">'T</span></span>

<span data-ttu-id="a20e3-113">Type du premier membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="a20e3-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="a20e3-114">'U</span><span class="sxs-lookup"><span data-stu-id="a20e3-114">'U</span></span>

<span data-ttu-id="a20e3-115">Type du deuxième membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="a20e3-115">The type of the pair's second member.</span></span>