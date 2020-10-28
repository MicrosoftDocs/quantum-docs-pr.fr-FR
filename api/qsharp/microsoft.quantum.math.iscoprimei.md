---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708375"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="326b9-102">IsCoprimeI fonction)</span><span class="sxs-lookup"><span data-stu-id="326b9-102">IsCoprimeI function</span></span>

<span data-ttu-id="326b9-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="326b9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="326b9-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="326b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="326b9-105">Retourne la valeur true si $a $ et $b $ sont copremier et false dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="326b9-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="326b9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="326b9-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="326b9-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="326b9-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="326b9-108">le premier nombre de co-primality en cours de test</span><span class="sxs-lookup"><span data-stu-id="326b9-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="326b9-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="326b9-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="326b9-110">deuxième nombre de primality en cours de test</span><span class="sxs-lookup"><span data-stu-id="326b9-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="326b9-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="326b9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="326b9-112">True si $a $ et $b $ sont copremier (par exemple, si leur plus grand diviseur commun est 1) et false dans le cas contraire</span><span class="sxs-lookup"><span data-stu-id="326b9-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>