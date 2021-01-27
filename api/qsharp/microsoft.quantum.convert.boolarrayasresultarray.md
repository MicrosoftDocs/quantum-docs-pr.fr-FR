---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834189"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="d26f5-102">BoolArrayAsResultArray fonction)</span><span class="sxs-lookup"><span data-stu-id="d26f5-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="d26f5-103">Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d26f5-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d26f5-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d26f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d26f5-105">Convertit un `Bool[]` type en un `Result[]` type, où `true` est mappé à `One` et `false` est mappé à `Zero` .</span><span class="sxs-lookup"><span data-stu-id="d26f5-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="d26f5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d26f5-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="d26f5-107">entrée : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d26f5-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d26f5-108">`Bool[]` à convertir.</span><span class="sxs-lookup"><span data-stu-id="d26f5-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d26f5-109">Sortie : [] __non valide <Result>__</span><span class="sxs-lookup"><span data-stu-id="d26f5-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="d26f5-110">`Result[]` représentant `input`.</span><span class="sxs-lookup"><span data-stu-id="d26f5-110">A `Result[]` representing the `input`.</span></span>