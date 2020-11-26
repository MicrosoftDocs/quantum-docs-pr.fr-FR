---
uid: Microsoft.Quantum.Canon.QFTLE
title: Opération QFTLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 460e43bc7997e9efad06c58ad14822e28cc45cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205573"
---
# <a name="qftle-operation"></a><span data-ttu-id="618a4-102">Opération QFTLE</span><span class="sxs-lookup"><span data-stu-id="618a4-102">QFTLE operation</span></span>

<span data-ttu-id="618a4-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="618a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="618a4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="618a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="618a4-105">Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Little endian.</span><span class="sxs-lookup"><span data-stu-id="618a4-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="618a4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="618a4-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="618a4-107">QS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="618a4-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="618a4-108">Registre quantique auquel la transformation de Fourier quantique est appliquée</span><span class="sxs-lookup"><span data-stu-id="618a4-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="618a4-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="618a4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="618a4-110">Notes</span><span class="sxs-lookup"><span data-stu-id="618a4-110">Remarks</span></span>

<span data-ttu-id="618a4-111">L’entrée et la sortie sont supposées être dans un encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="618a4-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="618a4-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="618a4-112">See Also</span></span>

- [<span data-ttu-id="618a4-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="618a4-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)