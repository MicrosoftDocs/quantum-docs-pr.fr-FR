---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853600"
---
# <a name="rangestep-function"></a><span data-ttu-id="97b36-102">RangeStep fonction)</span><span class="sxs-lookup"><span data-stu-id="97b36-102">RangeStep function</span></span>

<span data-ttu-id="97b36-103">Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="97b36-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="97b36-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="97b36-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="97b36-105">Retourne l’entier qui spécifie le mode de calcul de la valeur suivante d’une plage.</span><span class="sxs-lookup"><span data-stu-id="97b36-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="97b36-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="97b36-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="97b36-107">plage : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="97b36-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="97b36-108">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97b36-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97b36-109">Valeur de l’étape définie de la plage donnée.</span><span class="sxs-lookup"><span data-stu-id="97b36-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="97b36-110">Notes</span><span class="sxs-lookup"><span data-stu-id="97b36-110">Remarks</span></span>

<span data-ttu-id="97b36-111">Le premier élément d’une expression de plage est `start` , son deuxième élément est `start+step` , le troisième élément est `start+step+step` , etc., jusqu’à ce que `end` soit passé.</span><span class="sxs-lookup"><span data-stu-id="97b36-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>