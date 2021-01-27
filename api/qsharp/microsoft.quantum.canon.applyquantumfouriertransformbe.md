---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Opération ApplyQuantumFourierTransformBE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841565"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="e9fbf-102">Opération ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="e9fbf-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="e9fbf-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e9fbf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e9fbf-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9fbf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9fbf-105">Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Big-endian.</span><span class="sxs-lookup"><span data-stu-id="e9fbf-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e9fbf-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e9fbf-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="e9fbf-107">QS : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="e9fbf-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="e9fbf-108">Registre quantique auquel la transformation de Fourier quantique est appliquée</span><span class="sxs-lookup"><span data-stu-id="e9fbf-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9fbf-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9fbf-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e9fbf-110">Notes</span><span class="sxs-lookup"><span data-stu-id="e9fbf-110">Remarks</span></span>

<span data-ttu-id="e9fbf-111">L’entrée et la sortie sont supposées être en codage Big endian.</span><span class="sxs-lookup"><span data-stu-id="e9fbf-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9fbf-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9fbf-112">See Also</span></span>

- [<span data-ttu-id="e9fbf-113">Microsoft. Quantum. Canon. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="e9fbf-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="e9fbf-114">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="e9fbf-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)