---
uid: Microsoft.Quantum.Canon.QFTLE
title: Opération QFTLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703897"
---
# <a name="qftle-operation"></a><span data-ttu-id="33a83-102">Opération QFTLE</span><span class="sxs-lookup"><span data-stu-id="33a83-102">QFTLE operation</span></span>

<span data-ttu-id="33a83-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33a83-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33a83-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33a83-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33a83-105">Exécute la transformation de Fourier quantique sur un registre quantique contenant un entier dans la représentation Little endian.</span><span class="sxs-lookup"><span data-stu-id="33a83-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="33a83-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="33a83-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="33a83-107">QS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="33a83-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="33a83-108">Registre quantique auquel la transformation de Fourier quantique est appliquée</span><span class="sxs-lookup"><span data-stu-id="33a83-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="33a83-109">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33a83-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="33a83-110">Notes</span><span class="sxs-lookup"><span data-stu-id="33a83-110">Remarks</span></span>

<span data-ttu-id="33a83-111">L’entrée et la sortie sont supposées être dans un encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="33a83-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="33a83-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33a83-112">See Also</span></span>

- [<span data-ttu-id="33a83-113">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="33a83-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)