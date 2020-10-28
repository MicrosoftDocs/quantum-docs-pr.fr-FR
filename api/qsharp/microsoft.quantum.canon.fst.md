---
uid: Microsoft.Quantum.Canon.Fst
title: FST, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704179"
---
# <a name="fst-function"></a><span data-ttu-id="36cde-102">FST, fonction</span><span class="sxs-lookup"><span data-stu-id="36cde-102">Fst function</span></span>

<span data-ttu-id="36cde-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="36cde-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="36cde-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36cde-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36cde-105">À partir d’une paire, retourne son premier élément.</span><span class="sxs-lookup"><span data-stu-id="36cde-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="36cde-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="36cde-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="36cde-107">paire : ('t, 'U)</span><span class="sxs-lookup"><span data-stu-id="36cde-107">pair : ('T,'U)</span></span>

<span data-ttu-id="36cde-108">Tuple avec deux éléments.</span><span class="sxs-lookup"><span data-stu-id="36cde-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="36cde-109">Sortie : 't</span><span class="sxs-lookup"><span data-stu-id="36cde-109">Output : 'T</span></span>

<span data-ttu-id="36cde-110">Premier élément de `pair`.</span><span class="sxs-lookup"><span data-stu-id="36cde-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="36cde-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="36cde-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="36cde-112">Peut</span><span class="sxs-lookup"><span data-stu-id="36cde-112">'T</span></span>

<span data-ttu-id="36cde-113">Type du premier membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="36cde-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="36cde-114">'U</span><span class="sxs-lookup"><span data-stu-id="36cde-114">'U</span></span>

<span data-ttu-id="36cde-115">Type du deuxième membre de la paire.</span><span class="sxs-lookup"><span data-stu-id="36cde-115">The type of the pair's second member.</span></span>