---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEA
title: Opération ApplyLEOperationOnPhaseLEA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 572c66b201b6d2c816017230527c70c1b3c83371
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707614"
---
# <a name="applyleoperationonphaselea-operation"></a><span data-ttu-id="59d1f-102">Opération ApplyLEOperationOnPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="59d1f-102">ApplyLEOperationOnPhaseLEA operation</span></span>

<span data-ttu-id="59d1f-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="59d1f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="59d1f-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59d1f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59d1f-105">Applique une opération qui prend un <xref:microsoft.quantum.arithmetic.phaselittleendian> Registre comme entrée sur un registre cible de type <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="59d1f-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="59d1f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="59d1f-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="59d1f-107">opération : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="59d1f-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="59d1f-108">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="59d1f-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="59d1f-109">cible : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="59d1f-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="59d1f-110">Registre auquel l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="59d1f-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59d1f-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59d1f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="59d1f-112">Notes</span><span class="sxs-lookup"><span data-stu-id="59d1f-112">Remarks</span></span>

<span data-ttu-id="59d1f-113">Le Registre est transformé `LittleEndian` en en utilisant <xref:microsoft.quantum.canon.qftle> et est ensuite retourné à sa représentation d’origine après l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="59d1f-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="59d1f-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59d1f-114">See Also</span></span>

- [<span data-ttu-id="59d1f-115">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="59d1f-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="59d1f-116">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="59d1f-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="59d1f-117">Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="59d1f-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)