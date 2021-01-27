---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 384531137474562ebc8cc24dcd1ac976dc91ad9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832594"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="94c44-102">ResultArrayAsBoolArray fonction)</span><span class="sxs-lookup"><span data-stu-id="94c44-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="94c44-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="94c44-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="94c44-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94c44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94c44-105">Convertit un `Result[]` type en un `Bool[]` type, où `One` est mappé à `true` et `Zero` est mappé à `false` .</span><span class="sxs-lookup"><span data-stu-id="94c44-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="94c44-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="94c44-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="94c44-107">entrée : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="94c44-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="94c44-108">`Result[]` à convertir.</span><span class="sxs-lookup"><span data-stu-id="94c44-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="94c44-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="94c44-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="94c44-110">`Bool[]` représentant `input`.</span><span class="sxs-lookup"><span data-stu-id="94c44-110">A `Bool[]` representing the `input`.</span></span>