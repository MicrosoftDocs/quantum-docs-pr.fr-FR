---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210743"
---
# <a name="expmodl-function"></a><span data-ttu-id="a067c-102">ExpModL fonction)</span><span class="sxs-lookup"><span data-stu-id="a067c-102">ExpModL function</span></span>

<span data-ttu-id="a067c-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a067c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a067c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a067c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a067c-105">Retourne un entier élevé à une puissance donnée, par rapport à un modulo donné.</span><span class="sxs-lookup"><span data-stu-id="a067c-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="a067c-106">Description</span><span class="sxs-lookup"><span data-stu-id="a067c-106">Description</span></span>

<span data-ttu-id="a067c-107">Nous allons dénoter expBase par $x $, Power by $p $ et Modulo par $N $.</span><span class="sxs-lookup"><span data-stu-id="a067c-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="a067c-108">La fonction retourne $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="a067c-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="a067c-109">Nous supposons que $N $, $x $ sont positifs et que l’alimentation n’est pas négative.</span><span class="sxs-lookup"><span data-stu-id="a067c-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="a067c-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="a067c-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="a067c-111">expBase : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a067c-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="a067c-112">puissance : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a067c-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="a067c-113">modulo : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a067c-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="a067c-114">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a067c-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="a067c-115">Notes</span><span class="sxs-lookup"><span data-stu-id="a067c-115">Remarks</span></span>

<span data-ttu-id="a067c-116">Prend le temps proportionnel au nombre de bits dans `power` , et non à `power` lui-même.</span><span class="sxs-lookup"><span data-stu-id="a067c-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>