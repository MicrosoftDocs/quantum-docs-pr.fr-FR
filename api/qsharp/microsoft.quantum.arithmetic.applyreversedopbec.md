---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: Opération ApplyReversedOpBEC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 54c35ccea5e9c2d3ec7a3e6f325f78c3e602970e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707515"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="3e0f3-102">Opération ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="3e0f3-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="3e0f3-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3e0f3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3e0f3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e0f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e0f3-105">Applique une opération qui prend une entrée de poids fort (Big-endian) à un registre qui encode un entier non signé utilisant le format Little endian.</span><span class="sxs-lookup"><span data-stu-id="3e0f3-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="3e0f3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3e0f3-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="3e0f3-107">OP : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) d' => [unités](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="3e0f3-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3e0f3-108">Opération qui agit sur un registre Big endian.</span><span class="sxs-lookup"><span data-stu-id="3e0f3-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="3e0f3-109">inscription : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3e0f3-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3e0f3-110">Registre Little endian à transformer.</span><span class="sxs-lookup"><span data-stu-id="3e0f3-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e0f3-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e0f3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3e0f3-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e0f3-112">See Also</span></span>

- [<span data-ttu-id="3e0f3-113">Microsoft. Quantum. Arithmetic. ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="3e0f3-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="3e0f3-114">Microsoft. Quantum. Arithmetic. ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="3e0f3-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="3e0f3-115">Microsoft. Quantum. Arithmetic. ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="3e0f3-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)