---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLE
title: Opération ApplyLEOperationOnPhaseLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: ff8e9424b1fc179f25ca926520338a4bbbcd04c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707619"
---
# <a name="applyleoperationonphasele-operation"></a><span data-ttu-id="e2fe4-102">Opération ApplyLEOperationOnPhaseLE</span><span class="sxs-lookup"><span data-stu-id="e2fe4-102">ApplyLEOperationOnPhaseLE operation</span></span>

<span data-ttu-id="e2fe4-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e2fe4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e2fe4-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2fe4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2fe4-105">Applique une opération qui prend un <xref:microsoft.quantum.arithmetic.phaselittleendian> Registre comme entrée sur un registre cible de type <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="e2fe4-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="e2fe4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e2fe4-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="e2fe4-107">OP : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="e2fe4-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e2fe4-108">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="e2fe4-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="e2fe4-109">cible : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e2fe4-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e2fe4-110">Registre auquel l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="e2fe4-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2fe4-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2fe4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e2fe4-112">Notes</span><span class="sxs-lookup"><span data-stu-id="e2fe4-112">Remarks</span></span>

<span data-ttu-id="e2fe4-113">Le Registre est transformé `LittleEndian` en en utilisant <xref:microsoft.quantum.canon.qftle> et est ensuite retourné à sa représentation d’origine après l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="e2fe4-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2fe4-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2fe4-114">See Also</span></span>

- [<span data-ttu-id="e2fe4-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="e2fe4-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="e2fe4-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="e2fe4-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="e2fe4-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="e2fe4-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)