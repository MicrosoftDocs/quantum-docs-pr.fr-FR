---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Opération squarei
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842922"
---
# <a name="squaresi-operation"></a><span data-ttu-id="d4e40-102">Opération squarei</span><span class="sxs-lookup"><span data-stu-id="d4e40-102">SquareSI operation</span></span>

<span data-ttu-id="d4e40-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d4e40-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d4e40-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d4e40-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d4e40-105">Entier signé carré `xs` et stocke le résultat dans `result` , qui doit être initialement de zéro.</span><span class="sxs-lookup"><span data-stu-id="d4e40-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d4e40-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d4e40-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="d4e40-107">XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4e40-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="d4e40-108">entier n-bit vers carré (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4e40-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="d4e40-109">résultat : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4e40-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="d4e40-110">résultat de 2n bits (SignedLittleEndian), doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d4e40-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4e40-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4e40-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d4e40-112">Notes</span><span class="sxs-lookup"><span data-stu-id="d4e40-112">Remarks</span></span>

<span data-ttu-id="d4e40-113">L’implémentation s’appuie sur IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="d4e40-113">The implementation relies on IntegerSquare.</span></span>