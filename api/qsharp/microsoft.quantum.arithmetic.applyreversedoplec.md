---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: Opération ApplyReversedOpLEC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: ac9a6000140445a457a9abc46d5143dcb089883e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707494"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="97025-102">Opération ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="97025-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="97025-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="97025-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="97025-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97025-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97025-105">Applique une opération qui utilise l’entrée Little endian à un registre qui encode un entier non signé utilisant le format Big-endian.</span><span class="sxs-lookup"><span data-stu-id="97025-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="97025-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="97025-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="97025-107">OP : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) d' => [unités](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="97025-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="97025-108">Opération qui agit sur un registre Little endian.</span><span class="sxs-lookup"><span data-stu-id="97025-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="97025-109">inscription : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="97025-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="97025-110">Registre Big-endian à transformer.</span><span class="sxs-lookup"><span data-stu-id="97025-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97025-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97025-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="97025-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97025-112">See Also</span></span>

- [<span data-ttu-id="97025-113">Microsoft. Quantum. Arithmetic. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="97025-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="97025-114">Microsoft. Quantum. Arithmetic. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="97025-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="97025-115">Microsoft. Quantum. Arithmetic. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="97025-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)