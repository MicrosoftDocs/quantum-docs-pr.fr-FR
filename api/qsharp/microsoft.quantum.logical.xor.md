---
uid: Microsoft.Quantum.Logical.Xor
title: Xor, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708348"
---
# <a name="xor-function"></a><span data-ttu-id="cc147-102">Xor, fonction</span><span class="sxs-lookup"><span data-stu-id="cc147-102">Xor function</span></span>

<span data-ttu-id="cc147-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cc147-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cc147-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc147-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc147-105">Retourne la disjonction exclusive booléenne de deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="cc147-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="cc147-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="cc147-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="cc147-107">r : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc147-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc147-108">Première valeur à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="cc147-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="cc147-109">b : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc147-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc147-110">Deuxième valeur à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="cc147-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cc147-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cc147-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc147-112">`true` Si et seulement si un exactement de `a` et `b` est `true` .</span><span class="sxs-lookup"><span data-stu-id="cc147-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>