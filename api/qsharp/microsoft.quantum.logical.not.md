---
uid: Microsoft.Quantum.Logical.Not
title: Not, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701422"
---
# <a name="not-function"></a><span data-ttu-id="047a7-102">Not, fonction</span><span class="sxs-lookup"><span data-stu-id="047a7-102">Not function</span></span>

<span data-ttu-id="047a7-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="047a7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="047a7-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="047a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="047a7-105">Retourne la négation booléenne d’une valeur.</span><span class="sxs-lookup"><span data-stu-id="047a7-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="047a7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="047a7-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="047a7-107">valeur : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="047a7-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="047a7-108">Valeur à rendre négative.</span><span class="sxs-lookup"><span data-stu-id="047a7-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="047a7-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="047a7-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="047a7-110">`true` Si et seulement si `value` est `false` .</span><span class="sxs-lookup"><span data-stu-id="047a7-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="047a7-111">Notes</span><span class="sxs-lookup"><span data-stu-id="047a7-111">Remarks</span></span>

<span data-ttu-id="047a7-112">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="047a7-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```