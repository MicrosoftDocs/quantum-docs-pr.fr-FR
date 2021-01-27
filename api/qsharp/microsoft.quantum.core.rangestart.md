---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831114"
---
# <a name="rangestart-function"></a><span data-ttu-id="33bd0-102">RangeStart, fonction</span><span class="sxs-lookup"><span data-stu-id="33bd0-102">RangeStart function</span></span>

<span data-ttu-id="33bd0-103">Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="33bd0-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="33bd0-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="33bd0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="33bd0-105">Retourne la valeur de début définie de la plage donnée.</span><span class="sxs-lookup"><span data-stu-id="33bd0-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="33bd0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="33bd0-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="33bd0-107">plage : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="33bd0-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="33bd0-108">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="33bd0-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="33bd0-109">Valeur de début définie de la plage donnée.</span><span class="sxs-lookup"><span data-stu-id="33bd0-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="33bd0-110">Notes</span><span class="sxs-lookup"><span data-stu-id="33bd0-110">Remarks</span></span>

<span data-ttu-id="33bd0-111">Le premier élément d’une expression de plage est `start` , son deuxième élément est `start+step` , le troisième élément est `start+step+step` , etc., jusqu’à ce que `end` soit passé.</span><span class="sxs-lookup"><span data-stu-id="33bd0-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="33bd0-112">Notez que la valeur de début définie d’une plage est identique à celle du premier élément de la séquence, à moins que la plage spécifie une séquence vide (par exemple, 2.</span><span class="sxs-lookup"><span data-stu-id="33bd0-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="33bd0-113">1).</span><span class="sxs-lookup"><span data-stu-id="33bd0-113">1).</span></span>