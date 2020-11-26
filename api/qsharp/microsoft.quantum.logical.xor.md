---
uid: Microsoft.Quantum.Logical.Xor
title: Xor, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197090"
---
# <a name="xor-function"></a><span data-ttu-id="d3152-102">Xor, fonction</span><span class="sxs-lookup"><span data-stu-id="d3152-102">Xor function</span></span>

<span data-ttu-id="d3152-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d3152-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d3152-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3152-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3152-105">Retourne la disjonction exclusive booléenne de deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="d3152-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="d3152-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d3152-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="d3152-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d3152-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d3152-108">Première valeur à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="d3152-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="d3152-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d3152-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d3152-110">Deuxième valeur à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="d3152-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d3152-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d3152-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d3152-112">`true` Si et seulement si un exactement de `a` et `b` est `true` .</span><span class="sxs-lookup"><span data-stu-id="d3152-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>