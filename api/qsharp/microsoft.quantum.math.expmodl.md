---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708534"
---
# <a name="expmodl-function"></a><span data-ttu-id="12643-102">ExpModL fonction)</span><span class="sxs-lookup"><span data-stu-id="12643-102">ExpModL function</span></span>

<span data-ttu-id="12643-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="12643-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="12643-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12643-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12643-105">Retourne un entier élevé à une puissance donnée, par rapport à un modulo donné.</span><span class="sxs-lookup"><span data-stu-id="12643-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="12643-106">Description</span><span class="sxs-lookup"><span data-stu-id="12643-106">Description</span></span>

<span data-ttu-id="12643-107">Nous allons dénoter expBase par $x $, Power by $p $ et Modulo par $N $.</span><span class="sxs-lookup"><span data-stu-id="12643-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="12643-108">La fonction retourne $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="12643-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="12643-109">Nous supposons que $N $, $x $ sont positifs et que l’alimentation n’est pas négative.</span><span class="sxs-lookup"><span data-stu-id="12643-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="12643-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="12643-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="12643-111">expBase : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12643-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="12643-112">puissance : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12643-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="12643-113">modulo : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12643-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="12643-114">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12643-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="12643-115">Notes</span><span class="sxs-lookup"><span data-stu-id="12643-115">Remarks</span></span>

<span data-ttu-id="12643-116">Prend le temps proportionnel au nombre de bits dans `power` , et non à `power` lui-même.</span><span class="sxs-lookup"><span data-stu-id="12643-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>