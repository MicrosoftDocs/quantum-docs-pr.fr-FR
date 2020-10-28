---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702865"
---
# <a name="rangereverse-function"></a><span data-ttu-id="a3f63-102">RangeReverse fonction)</span><span class="sxs-lookup"><span data-stu-id="a3f63-102">RangeReverse function</span></span>

<span data-ttu-id="a3f63-103">Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="a3f63-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="a3f63-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3f63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3f63-105">Retourne une nouvelle plage qui est l’inverse de la plage d’entrée.</span><span class="sxs-lookup"><span data-stu-id="a3f63-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="a3f63-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a3f63-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="a3f63-107">r : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a3f63-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="a3f63-108">Plage d’entrée.</span><span class="sxs-lookup"><span data-stu-id="a3f63-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="a3f63-109">Sortie : [plage](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a3f63-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="a3f63-110">Nouvelle plage qui est l’inverse de la plage donnée.</span><span class="sxs-lookup"><span data-stu-id="a3f63-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3f63-111">Notes</span><span class="sxs-lookup"><span data-stu-id="a3f63-111">Remarks</span></span>

<span data-ttu-id="a3f63-112">Notez que l’inverse d’une plage n’est pas tout simplement `end` .. `-step` .. `start` , car le dernier élément réel d’une plage ne peut pas être le même que `end` .</span><span class="sxs-lookup"><span data-stu-id="a3f63-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>