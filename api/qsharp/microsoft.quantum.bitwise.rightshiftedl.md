---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842092"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="a85cd-102">RightShiftedL fonction)</span><span class="sxs-lookup"><span data-stu-id="a85cd-102">RightShiftedL function</span></span>

<span data-ttu-id="a85cd-103">Espace de noms : [Microsoft. Quantum. au niveau du bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="a85cd-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="a85cd-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a85cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a85cd-105">Déplace la représentation au niveau du bit d’un nombre vers la droite d’un nombre donné de bits.</span><span class="sxs-lookup"><span data-stu-id="a85cd-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="a85cd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a85cd-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="a85cd-107">valeur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a85cd-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a85cd-108">Nombre dont la représentation au niveau du bit doit être décalée vers la droite (moins significative).</span><span class="sxs-lookup"><span data-stu-id="a85cd-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="a85cd-109">montant : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a85cd-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a85cd-110">Nombre de bits par lequel doit `value` être décalé vers la droite.</span><span class="sxs-lookup"><span data-stu-id="a85cd-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="a85cd-111">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a85cd-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a85cd-112">Valeur de `value` , décalée vers la droite par `amount` bits.</span><span class="sxs-lookup"><span data-stu-id="a85cd-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="a85cd-113">Notes</span><span class="sxs-lookup"><span data-stu-id="a85cd-113">Remarks</span></span>

<span data-ttu-id="a85cd-114">Les éléments suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="a85cd-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```