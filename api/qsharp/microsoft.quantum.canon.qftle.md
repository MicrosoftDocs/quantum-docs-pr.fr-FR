---
uid: Microsoft.Quantum.Canon.QFTLE
title: Opération QFTLE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852274"
---
# <a name="qftle-operation"></a><span data-ttu-id="56a29-102">Opération QFTLE</span><span class="sxs-lookup"><span data-stu-id="56a29-102">QFTLE operation</span></span>

<span data-ttu-id="56a29-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56a29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56a29-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56a29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56a29-105">Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Little endian.</span><span class="sxs-lookup"><span data-stu-id="56a29-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="56a29-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="56a29-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="56a29-107">QS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="56a29-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="56a29-108">Registre quantique auquel la transformation de Fourier quantique est appliquée</span><span class="sxs-lookup"><span data-stu-id="56a29-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="56a29-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56a29-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="56a29-110">Notes</span><span class="sxs-lookup"><span data-stu-id="56a29-110">Remarks</span></span>

<span data-ttu-id="56a29-111">L’entrée et la sortie sont supposées être dans un encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="56a29-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="56a29-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56a29-112">See Also</span></span>

- [<span data-ttu-id="56a29-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="56a29-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)