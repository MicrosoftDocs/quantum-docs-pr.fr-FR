---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Opération AssertPhaseLessThan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707446"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="e423f-102">Opération AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="e423f-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="e423f-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e423f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e423f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e423f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e423f-105">Déclare que le `number` encodé dans PhaseLittleEndian est inférieur à `value` .</span><span class="sxs-lookup"><span data-stu-id="e423f-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="e423f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e423f-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="e423f-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e423f-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e423f-108">`number` doit être inférieur à ce.</span><span class="sxs-lookup"><span data-stu-id="e423f-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="e423f-109">nombre : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e423f-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e423f-110">Entier non signé qui est comparé à `value` .</span><span class="sxs-lookup"><span data-stu-id="e423f-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e423f-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e423f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e423f-112">Notes</span><span class="sxs-lookup"><span data-stu-id="e423f-112">Remarks</span></span>

<span data-ttu-id="e423f-113">La version contrôlée de cette opération ignore les contrôles.</span><span class="sxs-lookup"><span data-stu-id="e423f-113">The controlled version of this operation ignores controls.</span></span>