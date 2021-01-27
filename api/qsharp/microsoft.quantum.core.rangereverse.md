---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853661"
---
# <a name="rangereverse-function"></a><span data-ttu-id="40119-102">RangeReverse fonction)</span><span class="sxs-lookup"><span data-stu-id="40119-102">RangeReverse function</span></span>

<span data-ttu-id="40119-103">Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="40119-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="40119-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="40119-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="40119-105">Retourne une nouvelle plage qui est l’inverse de la plage d’entrée.</span><span class="sxs-lookup"><span data-stu-id="40119-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="40119-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="40119-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="40119-107">r : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="40119-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="40119-108">Plage d’entrée.</span><span class="sxs-lookup"><span data-stu-id="40119-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="40119-109">Sortie : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="40119-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="40119-110">Nouvelle plage qui est l’inverse de la plage donnée.</span><span class="sxs-lookup"><span data-stu-id="40119-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="40119-111">Notes</span><span class="sxs-lookup"><span data-stu-id="40119-111">Remarks</span></span>

<span data-ttu-id="40119-112">Notez que l’inverse d’une plage n’est pas tout simplement `end` .. `-step` .. `start` , car le dernier élément réel d’une plage ne peut pas être le même que `end` .</span><span class="sxs-lookup"><span data-stu-id="40119-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>