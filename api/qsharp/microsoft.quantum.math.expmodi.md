---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857030"
---
# <a name="expmodi-function"></a><span data-ttu-id="e1c70-102">ExpModI fonction)</span><span class="sxs-lookup"><span data-stu-id="e1c70-102">ExpModI function</span></span>

<span data-ttu-id="e1c70-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e1c70-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e1c70-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1c70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1c70-105">Retourne un entier élevé à une puissance donnée, par rapport à un modulo donné.</span><span class="sxs-lookup"><span data-stu-id="e1c70-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="e1c70-106">Description</span><span class="sxs-lookup"><span data-stu-id="e1c70-106">Description</span></span>

<span data-ttu-id="e1c70-107">Nous allons dénoter expBase par $x $, Power by $p $ et Modulo par $N $.</span><span class="sxs-lookup"><span data-stu-id="e1c70-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="e1c70-108">La fonction retourne $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="e1c70-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="e1c70-109">Nous supposons que $N $, $x $ sont positifs et que l’alimentation n’est pas négative.</span><span class="sxs-lookup"><span data-stu-id="e1c70-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="e1c70-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="e1c70-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="e1c70-111">expBase : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1c70-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="e1c70-112">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1c70-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="e1c70-113">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1c70-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="e1c70-114">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1c70-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="e1c70-115">Notes</span><span class="sxs-lookup"><span data-stu-id="e1c70-115">Remarks</span></span>

<span data-ttu-id="e1c70-116">Prend le temps proportionnel au nombre de bits dans `power` , et non à `power` lui-même.</span><span class="sxs-lookup"><span data-stu-id="e1c70-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>