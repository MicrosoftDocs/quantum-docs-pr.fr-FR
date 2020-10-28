---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702871"
---
# <a name="rangeend-function"></a><span data-ttu-id="b1e37-102">RangeEnd fonction)</span><span class="sxs-lookup"><span data-stu-id="b1e37-102">RangeEnd function</span></span>

<span data-ttu-id="b1e37-103">Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="b1e37-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="b1e37-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1e37-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1e37-105">Retourne la valeur de fin définie de la plage donnée, qui n’est pas nécessairement le dernier élément de la séquence.</span><span class="sxs-lookup"><span data-stu-id="b1e37-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="b1e37-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b1e37-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="b1e37-107">plage : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="b1e37-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="b1e37-108">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1e37-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1e37-109">Valeur de fin définie de la plage donnée.</span><span class="sxs-lookup"><span data-stu-id="b1e37-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1e37-110">Notes</span><span class="sxs-lookup"><span data-stu-id="b1e37-110">Remarks</span></span>

<span data-ttu-id="b1e37-111">Le premier élément d’une expression de plage est `start` , son deuxième élément est `start+step` , le troisième élément est `start+step+step` , etc., jusqu’à ce que `end` soit passé.</span><span class="sxs-lookup"><span data-stu-id="b1e37-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="b1e37-112">Notez que la valeur de fin définie d’une plage peut être différente de celle du dernier élément de la séquence spécifiée par la plage ; par exemple, dans une plage 0..</span><span class="sxs-lookup"><span data-stu-id="b1e37-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="b1e37-113">2..</span><span class="sxs-lookup"><span data-stu-id="b1e37-113">2 ..</span></span> <span data-ttu-id="b1e37-114">5 le dernier élément est 4, mais la valeur de fin est 5.</span><span class="sxs-lookup"><span data-stu-id="b1e37-114">5 the last element is 4 but the end value is 5.</span></span>