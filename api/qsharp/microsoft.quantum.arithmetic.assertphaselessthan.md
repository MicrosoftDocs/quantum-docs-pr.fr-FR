---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: Opération AssertPhaseLessThan
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843447"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="153a3-102">Opération AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="153a3-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="153a3-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="153a3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="153a3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="153a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="153a3-105">Déclare que le `number` encodé dans PhaseLittleEndian est inférieur à `value` .</span><span class="sxs-lookup"><span data-stu-id="153a3-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="153a3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="153a3-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="153a3-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="153a3-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="153a3-108">`number` doit être inférieur à ce.</span><span class="sxs-lookup"><span data-stu-id="153a3-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="153a3-109">nombre : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="153a3-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="153a3-110">Entier non signé qui est comparé à `value` .</span><span class="sxs-lookup"><span data-stu-id="153a3-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="153a3-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="153a3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="153a3-112">Notes</span><span class="sxs-lookup"><span data-stu-id="153a3-112">Remarks</span></span>

<span data-ttu-id="153a3-113">La version contrôlée de cette opération ignore les contrôles.</span><span class="sxs-lookup"><span data-stu-id="153a3-113">The controlled version of this operation ignores controls.</span></span>