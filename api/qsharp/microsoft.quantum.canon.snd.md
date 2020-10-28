---
uid: Microsoft.Quantum.Canon.Snd
title: Snd (fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703816"
---
# <a name="snd-function"></a><span data-ttu-id="59686-102">Snd (fonction)</span><span class="sxs-lookup"><span data-stu-id="59686-102">Snd function</span></span>

<span data-ttu-id="59686-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59686-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59686-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59686-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59686-105">À partir d’une paire, retourne son deuxième élément.</span><span class="sxs-lookup"><span data-stu-id="59686-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="59686-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="59686-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="59686-107">paire : ('t, 'U)</span><span class="sxs-lookup"><span data-stu-id="59686-107">pair : ('T,'U)</span></span>

<span data-ttu-id="59686-108">Tuple avec deux éléments.</span><span class="sxs-lookup"><span data-stu-id="59686-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="59686-109">Sortie : 'U</span><span class="sxs-lookup"><span data-stu-id="59686-109">Output : 'U</span></span>

<span data-ttu-id="59686-110">Deuxième élément de `pair` .</span><span class="sxs-lookup"><span data-stu-id="59686-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="59686-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="59686-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59686-112">Peut</span><span class="sxs-lookup"><span data-stu-id="59686-112">'T</span></span>

<span data-ttu-id="59686-113">Type du premier membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="59686-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="59686-114">'U</span><span class="sxs-lookup"><span data-stu-id="59686-114">'U</span></span>

<span data-ttu-id="59686-115">Type du deuxième membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="59686-115">The type of the pair's second member.</span></span>