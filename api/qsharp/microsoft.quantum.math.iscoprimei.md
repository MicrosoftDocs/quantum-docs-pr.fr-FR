---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851367"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="1031f-102">IsCoprimeI fonction)</span><span class="sxs-lookup"><span data-stu-id="1031f-102">IsCoprimeI function</span></span>

<span data-ttu-id="1031f-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1031f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1031f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1031f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1031f-105">Retourne la valeur true si $a $ et $b $ sont copremier et false dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="1031f-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="1031f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1031f-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="1031f-107">r : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1031f-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1031f-108">le premier nombre de co-primality en cours de test</span><span class="sxs-lookup"><span data-stu-id="1031f-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="1031f-109">b : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1031f-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1031f-110">deuxième nombre de primality en cours de test</span><span class="sxs-lookup"><span data-stu-id="1031f-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="1031f-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1031f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1031f-112">True si $a $ et $b $ sont copremier (par exemple, si leur plus grand diviseur commun est 1) et false dans le cas contraire</span><span class="sxs-lookup"><span data-stu-id="1031f-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>