---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705638"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="36c67-102">LeftShiftedI fonction)</span><span class="sxs-lookup"><span data-stu-id="36c67-102">LeftShiftedI function</span></span>

<span data-ttu-id="36c67-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="36c67-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="36c67-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36c67-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36c67-105">Déplace la représentation au niveau du bit d’un nombre laissé par un nombre donné de bits.</span><span class="sxs-lookup"><span data-stu-id="36c67-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="36c67-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="36c67-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="36c67-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36c67-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36c67-108">Nombre dont la représentation au niveau du bit doit être décalée vers la gauche (plus significative).</span><span class="sxs-lookup"><span data-stu-id="36c67-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="36c67-109">montant : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36c67-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36c67-110">Nombre de bits par lequel doit `value` être décalé vers la gauche.</span><span class="sxs-lookup"><span data-stu-id="36c67-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="36c67-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36c67-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36c67-112">Valeur de `value` , décalée vers la gauche par `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="36c67-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="36c67-113">Notes</span><span class="sxs-lookup"><span data-stu-id="36c67-113">Remarks</span></span>

<span data-ttu-id="36c67-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="36c67-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```