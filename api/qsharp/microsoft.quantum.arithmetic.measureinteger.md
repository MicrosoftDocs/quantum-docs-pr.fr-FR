---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Opération MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707174"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="c9a66-102">Opération MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="c9a66-102">MeasureInteger operation</span></span>

<span data-ttu-id="c9a66-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c9a66-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c9a66-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9a66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9a66-105">Mesure le contenu d’un registre quantique et le convertit en entier.</span><span class="sxs-lookup"><span data-stu-id="c9a66-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="c9a66-106">La mesure est effectuée par rapport à la base de calcul standard, c’est-à-dire le eigenbasis de `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="c9a66-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="c9a66-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c9a66-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="c9a66-108">cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9a66-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c9a66-109">Registre quantique dans l’encodage Little-endian.</span><span class="sxs-lookup"><span data-stu-id="c9a66-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="c9a66-110">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9a66-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9a66-111">Entier non signé qui contient la valeur mesurée de `target` .</span><span class="sxs-lookup"><span data-stu-id="c9a66-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9a66-112">Notes</span><span class="sxs-lookup"><span data-stu-id="c9a66-112">Remarks</span></span>

<span data-ttu-id="c9a66-113">Cette opération réinitialise son registre d’entrée à l’État $ \ket{00\cdots 0} $, pouvant être republiée sur un ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="c9a66-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9a66-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9a66-114">See Also</span></span>

- [<span data-ttu-id="c9a66-115">Microsoft. Quantum. Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="c9a66-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)