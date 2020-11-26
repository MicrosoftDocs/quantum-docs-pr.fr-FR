---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219666"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="1da15-102">LeftShiftedL fonction)</span><span class="sxs-lookup"><span data-stu-id="1da15-102">LeftShiftedL function</span></span>

<span data-ttu-id="1da15-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="1da15-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="1da15-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1da15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1da15-105">Déplace la représentation au niveau du bit d’un nombre laissé par un nombre donné de bits.</span><span class="sxs-lookup"><span data-stu-id="1da15-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="1da15-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1da15-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="1da15-107">valeur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1da15-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1da15-108">Nombre dont la représentation au niveau du bit doit être décalée vers la gauche (plus significative).</span><span class="sxs-lookup"><span data-stu-id="1da15-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="1da15-109">montant : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1da15-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1da15-110">Nombre de bits par lequel doit `value` être décalé vers la gauche.</span><span class="sxs-lookup"><span data-stu-id="1da15-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1da15-111">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1da15-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1da15-112">Valeur de `value` , décalée vers la gauche par `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="1da15-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="1da15-113">Notes</span><span class="sxs-lookup"><span data-stu-id="1da15-113">Remarks</span></span>

<span data-ttu-id="1da15-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="1da15-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```