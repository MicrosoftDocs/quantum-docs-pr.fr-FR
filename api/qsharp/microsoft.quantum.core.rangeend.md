---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224035"
---
# <a name="rangeend-function"></a><span data-ttu-id="9214d-102">RangeEnd fonction)</span><span class="sxs-lookup"><span data-stu-id="9214d-102">RangeEnd function</span></span>

<span data-ttu-id="9214d-103">Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="9214d-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="9214d-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9214d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9214d-105">Retourne la valeur de fin définie de la plage donnée, qui n’est pas nécessairement le dernier élément de la séquence.</span><span class="sxs-lookup"><span data-stu-id="9214d-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="9214d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9214d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="9214d-107">plage : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="9214d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="9214d-108">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9214d-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9214d-109">Valeur de fin définie de la plage donnée.</span><span class="sxs-lookup"><span data-stu-id="9214d-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="9214d-110">Notes</span><span class="sxs-lookup"><span data-stu-id="9214d-110">Remarks</span></span>

<span data-ttu-id="9214d-111">Le premier élément d’une expression de plage est `start` , son deuxième élément est `start+step` , le troisième élément est `start+step+step` , etc., jusqu’à ce que `end` soit passé.</span><span class="sxs-lookup"><span data-stu-id="9214d-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="9214d-112">Notez que la valeur de fin définie d’une plage peut être différente de celle du dernier élément de la séquence spécifiée par la plage ; par exemple, dans une plage 0..</span><span class="sxs-lookup"><span data-stu-id="9214d-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="9214d-113">2..</span><span class="sxs-lookup"><span data-stu-id="9214d-113">2 ..</span></span> <span data-ttu-id="9214d-114">5 le dernier élément est 4, mais la valeur de fin est 5.</span><span class="sxs-lookup"><span data-stu-id="9214d-114">5 the last element is 4 but the end value is 5.</span></span>