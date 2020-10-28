---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: Opération ApplyReversedOpBEA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: f606011dd002d6eadc4f882005f4577aeb28cac0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707518"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="e91d7-102">Opération ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="e91d7-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="e91d7-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e91d7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e91d7-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e91d7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e91d7-105">Applique une opération qui prend une entrée de poids fort (Big-endian) à un registre qui encode un entier non signé utilisant le format Little endian.</span><span class="sxs-lookup"><span data-stu-id="e91d7-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="e91d7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e91d7-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="e91d7-107">opération : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="e91d7-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e91d7-108">Opération qui agit sur un registre Big endian.</span><span class="sxs-lookup"><span data-stu-id="e91d7-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="e91d7-109">inscription : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e91d7-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e91d7-110">Registre Little endian à transformer.</span><span class="sxs-lookup"><span data-stu-id="e91d7-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e91d7-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e91d7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e91d7-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e91d7-112">See Also</span></span>

- [<span data-ttu-id="e91d7-113">Microsoft. Quantum. Arithmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="e91d7-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="e91d7-114">Microsoft. Quantum. Arithmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="e91d7-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="e91d7-115">Microsoft. Quantum. Arithmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="e91d7-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)