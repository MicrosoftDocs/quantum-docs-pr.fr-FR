---
uid: Microsoft.Quantum.Canon.QFT
title: Opération QFT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 8f1aa8c3680a068e500503ca25afa9a49e4ef5bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205527"
---
# <a name="qft-operation"></a><span data-ttu-id="3a6f4-102">Opération QFT</span><span class="sxs-lookup"><span data-stu-id="3a6f4-102">QFT operation</span></span>

<span data-ttu-id="3a6f4-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3a6f4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3a6f4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a6f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a6f4-105">Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Big-endian.</span><span class="sxs-lookup"><span data-stu-id="3a6f4-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3a6f4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3a6f4-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="3a6f4-107">QS : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="3a6f4-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="3a6f4-108">Registre quantique auquel la transformation de Fourier quantique est appliquée</span><span class="sxs-lookup"><span data-stu-id="3a6f4-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a6f4-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a6f4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3a6f4-110">Notes</span><span class="sxs-lookup"><span data-stu-id="3a6f4-110">Remarks</span></span>

<span data-ttu-id="3a6f4-111">L’entrée et la sortie sont supposées être en codage Big endian.</span><span class="sxs-lookup"><span data-stu-id="3a6f4-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a6f4-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a6f4-112">See Also</span></span>

- [<span data-ttu-id="3a6f4-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="3a6f4-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)