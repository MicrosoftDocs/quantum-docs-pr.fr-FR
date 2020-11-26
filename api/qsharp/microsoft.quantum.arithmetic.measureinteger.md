---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Opération MeasureInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222641"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="36f4d-102">Opération MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="36f4d-102">MeasureInteger operation</span></span>

<span data-ttu-id="36f4d-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="36f4d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="36f4d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36f4d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36f4d-105">Mesure le contenu d’un registre quantique et le convertit en entier.</span><span class="sxs-lookup"><span data-stu-id="36f4d-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="36f4d-106">La mesure est effectuée par rapport à la base de calcul standard, c’est-à-dire le eigenbasis de `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="36f4d-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="36f4d-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="36f4d-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="36f4d-108">cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="36f4d-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="36f4d-109">Registre quantique dans l’encodage Little-endian.</span><span class="sxs-lookup"><span data-stu-id="36f4d-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="36f4d-110">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36f4d-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36f4d-111">Entier non signé qui contient la valeur mesurée de `target` .</span><span class="sxs-lookup"><span data-stu-id="36f4d-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="36f4d-112">Notes</span><span class="sxs-lookup"><span data-stu-id="36f4d-112">Remarks</span></span>

<span data-ttu-id="36f4d-113">Cette opération réinitialise son registre d’entrée à l’État $ \ket{00\cdots 0} $, pouvant être republiée sur un ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="36f4d-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="36f4d-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="36f4d-114">See Also</span></span>

- [<span data-ttu-id="36f4d-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="36f4d-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)