---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705582"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="2bb65-102">RightShiftedI fonction)</span><span class="sxs-lookup"><span data-stu-id="2bb65-102">RightShiftedI function</span></span>

<span data-ttu-id="2bb65-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="2bb65-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="2bb65-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2bb65-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2bb65-105">Déplace la représentation au niveau du bit d’un nombre vers la droite d’un nombre donné de bits.</span><span class="sxs-lookup"><span data-stu-id="2bb65-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="2bb65-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2bb65-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="2bb65-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bb65-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bb65-108">Nombre dont la représentation au niveau du bit doit être décalée vers la droite (moins significative).</span><span class="sxs-lookup"><span data-stu-id="2bb65-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="2bb65-109">montant : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bb65-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bb65-110">Nombre de bits par lequel doit `value` être décalé vers la droite.</span><span class="sxs-lookup"><span data-stu-id="2bb65-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="2bb65-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bb65-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bb65-112">Valeur de `value` , décalée vers la droite par `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="2bb65-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="2bb65-113">Notes</span><span class="sxs-lookup"><span data-stu-id="2bb65-113">Remarks</span></span>

<span data-ttu-id="2bb65-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="2bb65-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```