---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 53131a755571ad1ac0a8a984bf229b16f67dbe51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195356"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="0178e-102">IsCoprimeI fonction)</span><span class="sxs-lookup"><span data-stu-id="0178e-102">IsCoprimeI function</span></span>

<span data-ttu-id="0178e-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0178e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0178e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0178e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0178e-105">Retourne la valeur true si $a $ et $b $ sont copremier et false dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="0178e-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="0178e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="0178e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="0178e-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0178e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0178e-108">le premier nombre de co-primality en cours de test</span><span class="sxs-lookup"><span data-stu-id="0178e-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="0178e-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0178e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0178e-110">deuxième nombre de primality en cours de test</span><span class="sxs-lookup"><span data-stu-id="0178e-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="0178e-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0178e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0178e-112">True si $a $ et $b $ sont copremier (par exemple, si leur plus grand diviseur commun est 1) et false dans le cas contraire</span><span class="sxs-lookup"><span data-stu-id="0178e-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>