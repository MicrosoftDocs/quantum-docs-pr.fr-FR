---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: f3af3abd4ee58f495d4ea60ec4f21a2690abec1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224222"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="ed96f-102">ResultArrayAsBoolArray fonction)</span><span class="sxs-lookup"><span data-stu-id="ed96f-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="ed96f-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ed96f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ed96f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed96f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed96f-105">Convertit un `Result[]` type en un `Bool[]` type, où `One` est mappé à `true` et `Zero` est mappé à `false` .</span><span class="sxs-lookup"><span data-stu-id="ed96f-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="ed96f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ed96f-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="ed96f-107">entrée : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="ed96f-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="ed96f-108">`Result[]` à convertir.</span><span class="sxs-lookup"><span data-stu-id="ed96f-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ed96f-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ed96f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="ed96f-110">`Bool[]` représentant `input`.</span><span class="sxs-lookup"><span data-stu-id="ed96f-110">A `Bool[]` representing the `input`.</span></span>