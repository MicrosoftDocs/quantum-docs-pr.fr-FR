---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845306"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="206c3-102">LeftShiftedI fonction)</span><span class="sxs-lookup"><span data-stu-id="206c3-102">LeftShiftedI function</span></span>

<span data-ttu-id="206c3-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="206c3-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="206c3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="206c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="206c3-105">Déplace la représentation au niveau du bit d’un nombre laissé par un nombre donné de bits.</span><span class="sxs-lookup"><span data-stu-id="206c3-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="206c3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="206c3-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="206c3-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="206c3-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="206c3-108">Nombre dont la représentation au niveau du bit doit être décalée vers la gauche (plus significative).</span><span class="sxs-lookup"><span data-stu-id="206c3-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="206c3-109">montant : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="206c3-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="206c3-110">Nombre de bits par lequel doit `value` être décalé vers la gauche.</span><span class="sxs-lookup"><span data-stu-id="206c3-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="206c3-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="206c3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="206c3-112">Valeur de `value` , décalée vers la gauche par `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="206c3-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="206c3-113">Notes</span><span class="sxs-lookup"><span data-stu-id="206c3-113">Remarks</span></span>

<span data-ttu-id="206c3-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="206c3-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```