---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Opération IncrementByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707270"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="2c14b-102">Opération IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="2c14b-102">IncrementByInteger operation</span></span>

<span data-ttu-id="2c14b-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2c14b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2c14b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c14b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c14b-105">Incrémente un registre quantique non signé par un entier classique, à l’aide de rotations de phase.</span><span class="sxs-lookup"><span data-stu-id="2c14b-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="2c14b-106">Description</span><span class="sxs-lookup"><span data-stu-id="2c14b-106">Description</span></span>

<span data-ttu-id="2c14b-107">Supposons que `target` encode un entier non signé $x $ dans un encodage Little endian et qu' `increment` il est égal à $a $.</span><span class="sxs-lookup"><span data-stu-id="2c14b-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="2c14b-108">Ensuite, cette opération implémente l’unité $ \ket{x} \mapsto \ket{x + a} $, où l’ajout est effectué modulo $2 ^ n $, où $n = \texttt{Length (target !)} $.</span><span class="sxs-lookup"><span data-stu-id="2c14b-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="2c14b-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="2c14b-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="2c14b-110">incrément : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2c14b-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2c14b-111">Entier par lequel `target` est incrémenté.</span><span class="sxs-lookup"><span data-stu-id="2c14b-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="2c14b-112">cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2c14b-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2c14b-113">Un registre Quantum codant un entier non signé utilisant l’encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="2c14b-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c14b-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c14b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
