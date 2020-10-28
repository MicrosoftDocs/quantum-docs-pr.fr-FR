---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Opération squarei
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706219"
---
# <a name="squaresi-operation"></a><span data-ttu-id="62f75-102">Opération squarei</span><span class="sxs-lookup"><span data-stu-id="62f75-102">SquareSI operation</span></span>

<span data-ttu-id="62f75-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="62f75-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="62f75-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62f75-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62f75-105">Entier signé carré `xs` et stocke le résultat dans `result` , qui doit être initialement de zéro.</span><span class="sxs-lookup"><span data-stu-id="62f75-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="62f75-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="62f75-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="62f75-107">XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62f75-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="62f75-108">entier n-bit vers carré (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62f75-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="62f75-109">résultat : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62f75-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="62f75-110">résultat de 2n bits (SignedLittleEndian), doit être initialement à l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="62f75-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62f75-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62f75-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="62f75-112">Notes</span><span class="sxs-lookup"><span data-stu-id="62f75-112">Remarks</span></span>

<span data-ttu-id="62f75-113">L’implémentation s’appuie sur IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="62f75-113">The implementation relies on IntegerSquare.</span></span>