---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228132"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="55691-102">IsCoprimeL fonction)</span><span class="sxs-lookup"><span data-stu-id="55691-102">IsCoprimeL function</span></span>

<span data-ttu-id="55691-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="55691-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="55691-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55691-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55691-105">Retourne la valeur true si $a $ et $b $ sont copremier et false dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="55691-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="55691-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="55691-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="55691-107">r : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="55691-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="55691-108">le premier nombre de co-primality en cours de test</span><span class="sxs-lookup"><span data-stu-id="55691-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="55691-109">b : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="55691-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="55691-110">deuxième nombre de primality en cours de test</span><span class="sxs-lookup"><span data-stu-id="55691-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="55691-111">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="55691-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="55691-112">True si $a $ et $b $ sont copremier (par exemple, si leur plus grand diviseur commun est 1) et false dans le cas contraire</span><span class="sxs-lookup"><span data-stu-id="55691-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>