---
uid: Microsoft.Quantum.Math.PlusA
title: Fonction plus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194829"
---
# <a name="plusa-function"></a><span data-ttu-id="988cc-102">Fonction plus</span><span class="sxs-lookup"><span data-stu-id="988cc-102">PlusA function</span></span>

<span data-ttu-id="988cc-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="988cc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="988cc-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="988cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="988cc-105">Retourne la somme (concaténation) de deux entrées.</span><span class="sxs-lookup"><span data-stu-id="988cc-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="988cc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="988cc-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="988cc-107">r : 'élément []</span><span class="sxs-lookup"><span data-stu-id="988cc-107">a : 'Element[]</span></span>

<span data-ttu-id="988cc-108">Première entrée $a $ à additionner.</span><span class="sxs-lookup"><span data-stu-id="988cc-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="988cc-109">b : 'élément []</span><span class="sxs-lookup"><span data-stu-id="988cc-109">b : 'Element[]</span></span>

<span data-ttu-id="988cc-110">Deuxième entrée $b $ à additionner.</span><span class="sxs-lookup"><span data-stu-id="988cc-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="988cc-111">Sortie : 'Element []</span><span class="sxs-lookup"><span data-stu-id="988cc-111">Output : 'Element[]</span></span>

<span data-ttu-id="988cc-112">Somme $a + b $.</span><span class="sxs-lookup"><span data-stu-id="988cc-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="988cc-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="988cc-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="988cc-114">', Élément</span><span class="sxs-lookup"><span data-stu-id="988cc-114">'Element</span></span>

<span data-ttu-id="988cc-115">Type de chaque élément dans chacun des deux tableaux d’entrée.</span><span class="sxs-lookup"><span data-stu-id="988cc-115">The type of each element in each of the two input arrays.</span></span>