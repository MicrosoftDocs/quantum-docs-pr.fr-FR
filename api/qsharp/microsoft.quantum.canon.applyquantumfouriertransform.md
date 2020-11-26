---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Opération ApplyQuantumFourierTransform
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 6d3ad9ca2e0d10c264f8020e1f34687f6cbc9f94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218187"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="fa595-102">Opération ApplyQuantumFourierTransform</span><span class="sxs-lookup"><span data-stu-id="fa595-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="fa595-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fa595-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fa595-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa595-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa595-105">Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Little endian.</span><span class="sxs-lookup"><span data-stu-id="fa595-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fa595-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fa595-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="fa595-107">QS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fa595-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fa595-108">Registre quantique auquel la transformation de Fourier quantique est appliquée</span><span class="sxs-lookup"><span data-stu-id="fa595-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa595-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa595-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fa595-110">Notes</span><span class="sxs-lookup"><span data-stu-id="fa595-110">Remarks</span></span>

<span data-ttu-id="fa595-111">L’entrée et la sortie sont supposées être dans un encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="fa595-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa595-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa595-112">See Also</span></span>

- [<span data-ttu-id="fa595-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="fa595-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)