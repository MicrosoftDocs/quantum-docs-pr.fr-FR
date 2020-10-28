---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Opération CompareGTSI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707382"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="27422-102">Opération CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="27422-102">CompareGTSI operation</span></span>

<span data-ttu-id="27422-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="27422-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="27422-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27422-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27422-105">Wrapper pour comparaison d’entiers signés : `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="27422-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="27422-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="27422-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="27422-107">XS : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="27422-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="27422-108">Premier $n nombre de bits</span><span class="sxs-lookup"><span data-stu-id="27422-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="27422-109">distinctes : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="27422-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="27422-110">Deuxième $n nombre de $ bits</span><span class="sxs-lookup"><span data-stu-id="27422-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="27422-111">résultat : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27422-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27422-112">Est retourné si $xs > distinctes $</span><span class="sxs-lookup"><span data-stu-id="27422-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="27422-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27422-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

