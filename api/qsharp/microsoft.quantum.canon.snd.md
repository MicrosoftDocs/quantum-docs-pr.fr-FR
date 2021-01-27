---
uid: Microsoft.Quantum.Canon.Snd
title: Snd (fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852156"
---
# <a name="snd-function"></a><span data-ttu-id="a1f7e-102">Snd (fonction)</span><span class="sxs-lookup"><span data-stu-id="a1f7e-102">Snd function</span></span>

<span data-ttu-id="a1f7e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a1f7e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a1f7e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1f7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1f7e-105">À partir d’une paire, retourne son deuxième élément.</span><span class="sxs-lookup"><span data-stu-id="a1f7e-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="a1f7e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a1f7e-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="a1f7e-107">paire : ('t, 'U)</span><span class="sxs-lookup"><span data-stu-id="a1f7e-107">pair : ('T,'U)</span></span>

<span data-ttu-id="a1f7e-108">Tuple avec deux éléments.</span><span class="sxs-lookup"><span data-stu-id="a1f7e-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="a1f7e-109">Sortie : 'U</span><span class="sxs-lookup"><span data-stu-id="a1f7e-109">Output : 'U</span></span>

<span data-ttu-id="a1f7e-110">Deuxième élément de `pair` .</span><span class="sxs-lookup"><span data-stu-id="a1f7e-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a1f7e-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a1f7e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a1f7e-112">Peut</span><span class="sxs-lookup"><span data-stu-id="a1f7e-112">'T</span></span>

<span data-ttu-id="a1f7e-113">Type du premier membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="a1f7e-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="a1f7e-114">'U</span><span class="sxs-lookup"><span data-stu-id="a1f7e-114">'U</span></span>

<span data-ttu-id="a1f7e-115">Type du deuxième membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="a1f7e-115">The type of the pair's second member.</span></span>