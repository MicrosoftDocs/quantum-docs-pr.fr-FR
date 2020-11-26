---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219513"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="572ee-102">RightShiftedL fonction)</span><span class="sxs-lookup"><span data-stu-id="572ee-102">RightShiftedL function</span></span>

<span data-ttu-id="572ee-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="572ee-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="572ee-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="572ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="572ee-105">Déplace la représentation au niveau du bit d’un nombre vers la droite d’un nombre donné de bits.</span><span class="sxs-lookup"><span data-stu-id="572ee-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="572ee-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="572ee-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="572ee-107">valeur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="572ee-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="572ee-108">Nombre dont la représentation au niveau du bit doit être décalée vers la droite (moins significative).</span><span class="sxs-lookup"><span data-stu-id="572ee-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="572ee-109">montant : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="572ee-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="572ee-110">Nombre de bits par lequel doit `value` être décalé vers la droite.</span><span class="sxs-lookup"><span data-stu-id="572ee-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="572ee-111">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="572ee-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="572ee-112">Valeur de `value` , décalée vers la droite par `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="572ee-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="572ee-113">Notes</span><span class="sxs-lookup"><span data-stu-id="572ee-113">Remarks</span></span>

<span data-ttu-id="572ee-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="572ee-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```