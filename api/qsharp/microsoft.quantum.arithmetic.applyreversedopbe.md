---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: Opération ApplyReversedOpBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: a181cb16d6ae7684d49fe200d72bcbf5209018e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707539"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="29f5c-102">Opération ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="29f5c-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="29f5c-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="29f5c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="29f5c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29f5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29f5c-105">Applique une opération qui prend une entrée de poids fort (Big-endian) à un registre qui encode un entier non signé utilisant le format Little endian.</span><span class="sxs-lookup"><span data-stu-id="29f5c-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="29f5c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="29f5c-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="29f5c-107">OP : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) bigEndian</span><span class="sxs-lookup"><span data-stu-id="29f5c-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="29f5c-108">Opération qui agit sur un registre Big endian.</span><span class="sxs-lookup"><span data-stu-id="29f5c-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="29f5c-109">inscription : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="29f5c-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="29f5c-110">Registre Little endian à transformer.</span><span class="sxs-lookup"><span data-stu-id="29f5c-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29f5c-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29f5c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="29f5c-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29f5c-112">See Also</span></span>

- [<span data-ttu-id="29f5c-113">Microsoft. Quantum. Arithmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="29f5c-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="29f5c-114">Microsoft. Quantum. Arithmetic. ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="29f5c-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="29f5c-115">Microsoft. Quantum. Arithmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="29f5c-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)