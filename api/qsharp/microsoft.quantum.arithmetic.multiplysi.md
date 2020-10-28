---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Opération MultiplySI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706363"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="1d0ea-102">Opération MultiplySI</span><span class="sxs-lookup"><span data-stu-id="1d0ea-102">MultiplySI operation</span></span>

<span data-ttu-id="1d0ea-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1d0ea-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1d0ea-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d0ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d0ea-105">Multiplie un entier signé `xs` par `ys` un entier signé et stocke le résultat dans `result` , qui doit être initialement de zéro.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="1d0ea-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1d0ea-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="1d0ea-107">XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d0ea-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="1d0ea-108">multiplicande n bits (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d0ea-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="1d0ea-109">distinctes : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d0ea-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="1d0ea-110">multiplicateur n-bit (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d0ea-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="1d0ea-111">résultat : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d0ea-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="1d0ea-112">résultat de 2n bits (SignedLittleEndian), doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="1d0ea-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d0ea-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d0ea-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

