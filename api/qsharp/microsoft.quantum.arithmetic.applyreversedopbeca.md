---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: Opération ApplyReversedOpBECA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1a11b85e4eca627246d7b9d3b4c10824296e9a77
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707510"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="14898-102">Opération ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="14898-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="14898-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="14898-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="14898-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14898-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14898-105">Applique une opération qui prend une entrée de poids fort (Big-endian) à un registre qui encode un entier non signé utilisant le format Little endian.</span><span class="sxs-lookup"><span data-stu-id="14898-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="14898-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="14898-106">Input</span></span>

### <a name="op--bigendian--unit-ctl--adj"></a><span data-ttu-id="14898-107">OP : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) d' => [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="14898-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="14898-108">Opération qui agit sur un registre Big endian.</span><span class="sxs-lookup"><span data-stu-id="14898-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="14898-109">inscription : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="14898-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="14898-110">Registre Little endian à transformer.</span><span class="sxs-lookup"><span data-stu-id="14898-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14898-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14898-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="14898-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14898-112">See Also</span></span>

- [<span data-ttu-id="14898-113">Microsoft. Quantum. Arithmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="14898-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="14898-114">Microsoft. Quantum. Arithmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="14898-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="14898-115">Microsoft. Quantum. Arithmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="14898-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)