---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705579"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="513b5-102">RightShiftedL fonction)</span><span class="sxs-lookup"><span data-stu-id="513b5-102">RightShiftedL function</span></span>

<span data-ttu-id="513b5-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="513b5-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="513b5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="513b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="513b5-105">Déplace la représentation au niveau du bit d’un nombre vers la droite d’un nombre donné de bits.</span><span class="sxs-lookup"><span data-stu-id="513b5-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="513b5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="513b5-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="513b5-107">valeur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="513b5-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="513b5-108">Nombre dont la représentation au niveau du bit doit être décalée vers la droite (moins significative).</span><span class="sxs-lookup"><span data-stu-id="513b5-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="513b5-109">montant : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="513b5-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="513b5-110">Nombre de bits par lequel doit `value` être décalé vers la droite.</span><span class="sxs-lookup"><span data-stu-id="513b5-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="513b5-111">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="513b5-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="513b5-112">Valeur de `value` , décalée vers la droite par `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="513b5-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="513b5-113">Notes</span><span class="sxs-lookup"><span data-stu-id="513b5-113">Remarks</span></span>

<span data-ttu-id="513b5-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="513b5-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```