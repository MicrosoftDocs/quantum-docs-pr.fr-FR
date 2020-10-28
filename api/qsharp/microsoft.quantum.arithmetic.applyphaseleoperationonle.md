---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: Opération ApplyPhaseLEOperationOnLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: dacc52766cf72d2bd562b76fc4939f962133e9a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707563"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="82898-102">Opération ApplyPhaseLEOperationOnLE</span><span class="sxs-lookup"><span data-stu-id="82898-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="82898-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="82898-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="82898-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82898-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82898-105">Applique une opération qui prend un <xref:microsoft.quantum.arithmetic.littleendian> Registre comme entrée sur un registre cible de type <xref:microsoft.quantum.arithmetic.phaselittleendian> .</span><span class="sxs-lookup"><span data-stu-id="82898-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="82898-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="82898-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="82898-107">OP : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="82898-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="82898-108">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="82898-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="82898-109">cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="82898-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="82898-110">Registre auquel l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="82898-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82898-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82898-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="82898-112">Notes</span><span class="sxs-lookup"><span data-stu-id="82898-112">Remarks</span></span>

<span data-ttu-id="82898-113">Le Registre est transformé `PhaseLittleEndian` en en utilisant <xref:microsoft.quantum.canon.qftle> et est ensuite retourné à sa représentation d’origine après l’application de `op` .</span><span class="sxs-lookup"><span data-stu-id="82898-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="82898-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82898-114">See Also</span></span>

- [<span data-ttu-id="82898-115">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="82898-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="82898-116">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="82898-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="82898-117">Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="82898-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)