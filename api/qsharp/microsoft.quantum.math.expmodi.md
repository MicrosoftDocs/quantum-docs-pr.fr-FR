---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228488"
---
# <a name="expmodi-function"></a><span data-ttu-id="0a36f-102">ExpModI fonction)</span><span class="sxs-lookup"><span data-stu-id="0a36f-102">ExpModI function</span></span>

<span data-ttu-id="0a36f-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0a36f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0a36f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a36f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a36f-105">Retourne un entier élevé à une puissance donnée, par rapport à un modulo donné.</span><span class="sxs-lookup"><span data-stu-id="0a36f-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="0a36f-106">Description</span><span class="sxs-lookup"><span data-stu-id="0a36f-106">Description</span></span>

<span data-ttu-id="0a36f-107">Nous allons dénoter expBase par $x $, Power by $p $ et Modulo par $N $.</span><span class="sxs-lookup"><span data-stu-id="0a36f-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="0a36f-108">La fonction retourne $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="0a36f-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="0a36f-109">Nous supposons que $N $, $x $ sont positifs et que l’alimentation n’est pas négative.</span><span class="sxs-lookup"><span data-stu-id="0a36f-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="0a36f-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="0a36f-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="0a36f-111">expBase : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a36f-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="0a36f-112">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a36f-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="0a36f-113">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a36f-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="0a36f-114">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a36f-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="0a36f-115">Notes</span><span class="sxs-lookup"><span data-stu-id="0a36f-115">Remarks</span></span>

<span data-ttu-id="0a36f-116">Prend le temps proportionnel au nombre de bits dans `power` , et non à `power` lui-même.</span><span class="sxs-lookup"><span data-stu-id="0a36f-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>