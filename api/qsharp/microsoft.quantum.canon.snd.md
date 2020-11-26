---
uid: Microsoft.Quantum.Canon.Snd
title: Snd (fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205318"
---
# <a name="snd-function"></a><span data-ttu-id="fe583-102">Snd (fonction)</span><span class="sxs-lookup"><span data-stu-id="fe583-102">Snd function</span></span>

<span data-ttu-id="fe583-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fe583-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fe583-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe583-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe583-105">À partir d’une paire, retourne son deuxième élément.</span><span class="sxs-lookup"><span data-stu-id="fe583-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="fe583-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fe583-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="fe583-107">paire : ('t, 'U)</span><span class="sxs-lookup"><span data-stu-id="fe583-107">pair : ('T,'U)</span></span>

<span data-ttu-id="fe583-108">Tuple avec deux éléments.</span><span class="sxs-lookup"><span data-stu-id="fe583-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="fe583-109">Sortie : 'U</span><span class="sxs-lookup"><span data-stu-id="fe583-109">Output : 'U</span></span>

<span data-ttu-id="fe583-110">Deuxième élément de `pair` .</span><span class="sxs-lookup"><span data-stu-id="fe583-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fe583-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="fe583-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe583-112">Peut</span><span class="sxs-lookup"><span data-stu-id="fe583-112">'T</span></span>

<span data-ttu-id="fe583-113">Type du premier membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="fe583-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="fe583-114">'U</span><span class="sxs-lookup"><span data-stu-id="fe583-114">'U</span></span>

<span data-ttu-id="fe583-115">Type du deuxième membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="fe583-115">The type of the pair's second member.</span></span>