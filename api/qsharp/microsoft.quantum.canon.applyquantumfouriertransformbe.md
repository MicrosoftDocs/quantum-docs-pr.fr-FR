---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Opération ApplyQuantumFourierTransformBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705094"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="23d3d-102">Opération ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="23d3d-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="23d3d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="23d3d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="23d3d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23d3d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23d3d-105">Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Big-endian.</span><span class="sxs-lookup"><span data-stu-id="23d3d-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="23d3d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="23d3d-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="23d3d-107">QS : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="23d3d-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="23d3d-108">Registre quantique auquel la transformation de Fourier quantique est appliquée</span><span class="sxs-lookup"><span data-stu-id="23d3d-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="23d3d-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23d3d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="23d3d-110">Notes</span><span class="sxs-lookup"><span data-stu-id="23d3d-110">Remarks</span></span>

<span data-ttu-id="23d3d-111">L’entrée et la sortie sont supposées être en codage Big endian.</span><span class="sxs-lookup"><span data-stu-id="23d3d-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="23d3d-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23d3d-112">See Also</span></span>

- [<span data-ttu-id="23d3d-113">Microsoft. Quantum. Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="23d3d-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="23d3d-114">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="23d3d-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)