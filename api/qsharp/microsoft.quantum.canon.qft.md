---
uid: Microsoft.Quantum.Canon.QFT
title: Opération QFT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703903"
---
# <a name="qft-operation"></a><span data-ttu-id="c43bc-102">Opération QFT</span><span class="sxs-lookup"><span data-stu-id="c43bc-102">QFT operation</span></span>

<span data-ttu-id="c43bc-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c43bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c43bc-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c43bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c43bc-105">Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Big-endian.</span><span class="sxs-lookup"><span data-stu-id="c43bc-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c43bc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c43bc-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="c43bc-107">QS : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="c43bc-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="c43bc-108">Registre quantique auquel la transformation de Fourier quantique est appliquée</span><span class="sxs-lookup"><span data-stu-id="c43bc-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="c43bc-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c43bc-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c43bc-110">Notes</span><span class="sxs-lookup"><span data-stu-id="c43bc-110">Remarks</span></span>

<span data-ttu-id="c43bc-111">L’entrée et la sortie sont supposées être en codage Big endian.</span><span class="sxs-lookup"><span data-stu-id="c43bc-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="c43bc-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c43bc-112">See Also</span></span>

- [<span data-ttu-id="c43bc-113">Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="c43bc-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)