---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845253"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="c7e6d-102">RightShiftedI fonction)</span><span class="sxs-lookup"><span data-stu-id="c7e6d-102">RightShiftedI function</span></span>

<span data-ttu-id="c7e6d-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="c7e6d-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="c7e6d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c7e6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c7e6d-105">Déplace la représentation au niveau du bit d’un nombre vers la droite d’un nombre donné de bits.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="c7e6d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c7e6d-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="c7e6d-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7e6d-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7e6d-108">Nombre dont la représentation au niveau du bit doit être décalée vers la droite (moins significative).</span><span class="sxs-lookup"><span data-stu-id="c7e6d-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="c7e6d-109">montant : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7e6d-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7e6d-110">Nombre de bits par lequel doit `value` être décalé vers la droite.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="c7e6d-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c7e6d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c7e6d-112">Valeur de `value` , décalée vers la droite par `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="c7e6d-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7e6d-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c7e6d-113">Remarks</span></span>

<span data-ttu-id="c7e6d-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="c7e6d-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```