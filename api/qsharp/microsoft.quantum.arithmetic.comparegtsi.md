---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Opération CompareGTSI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: a0e8ef66f1e1a62d4f6a78364135376810507534
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223491"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="e4c66-102">Opération CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="e4c66-102">CompareGTSI operation</span></span>

<span data-ttu-id="e4c66-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e4c66-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e4c66-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="e4c66-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="e4c66-105">Wrapper pour comparaison d’entiers signés : `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="e4c66-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e4c66-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e4c66-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="e4c66-107">XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e4c66-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="e4c66-108">Premier $n nombre de bits</span><span class="sxs-lookup"><span data-stu-id="e4c66-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="e4c66-109">distinctes : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e4c66-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="e4c66-110">Deuxième $n nombre de $ bits</span><span class="sxs-lookup"><span data-stu-id="e4c66-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="e4c66-111">résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e4c66-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e4c66-112">Est retourné si $xs > distinctes $</span><span class="sxs-lookup"><span data-stu-id="e4c66-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4c66-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4c66-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

