---
uid: Microsoft.Quantum.Canon.Fst
title: FST, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840513"
---
# <a name="fst-function"></a><span data-ttu-id="d038f-102">FST, fonction</span><span class="sxs-lookup"><span data-stu-id="d038f-102">Fst function</span></span>

<span data-ttu-id="d038f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d038f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d038f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d038f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d038f-105">À partir d’une paire, retourne son premier élément.</span><span class="sxs-lookup"><span data-stu-id="d038f-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="d038f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d038f-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="d038f-107">paire : ('t, 'U)</span><span class="sxs-lookup"><span data-stu-id="d038f-107">pair : ('T,'U)</span></span>

<span data-ttu-id="d038f-108">Tuple avec deux éléments.</span><span class="sxs-lookup"><span data-stu-id="d038f-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="d038f-109">Sortie : 't</span><span class="sxs-lookup"><span data-stu-id="d038f-109">Output : 'T</span></span>

<span data-ttu-id="d038f-110">Premier élément de `pair`.</span><span class="sxs-lookup"><span data-stu-id="d038f-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d038f-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d038f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d038f-112">Peut</span><span class="sxs-lookup"><span data-stu-id="d038f-112">'T</span></span>

<span data-ttu-id="d038f-113">Type du premier membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="d038f-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="d038f-114">'U</span><span class="sxs-lookup"><span data-stu-id="d038f-114">'U</span></span>

<span data-ttu-id="d038f-115">Type du deuxième membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="d038f-115">The type of the pair's second member.</span></span>