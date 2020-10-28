---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Opération IncrementPhaseByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707246"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="d6aaf-102">Opération IncrementPhaseByInteger</span><span class="sxs-lookup"><span data-stu-id="d6aaf-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="d6aaf-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d6aaf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d6aaf-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6aaf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6aaf-105">Incrémente un registre quantique non signé par un entier classique, à l’aide de rotations de phase.</span><span class="sxs-lookup"><span data-stu-id="d6aaf-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="d6aaf-106">Description</span><span class="sxs-lookup"><span data-stu-id="d6aaf-106">Description</span></span>

<span data-ttu-id="d6aaf-107">Supposons que `target` encode un entier non signé $x $ dans un encodage Little endian et qu' `increment` il est égal à $a $.</span><span class="sxs-lookup"><span data-stu-id="d6aaf-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="d6aaf-108">Ensuite, cette opération implémente l’unité $ \ket{x} \mapsto \ket{x + a} $, où l’ajout est effectué modulo $2 ^ n $, où $n = \texttt{Length (target !)} $.</span><span class="sxs-lookup"><span data-stu-id="d6aaf-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="d6aaf-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="d6aaf-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="d6aaf-110">incrément : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6aaf-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6aaf-111">Entier par lequel `target` est incrémenté.</span><span class="sxs-lookup"><span data-stu-id="d6aaf-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="d6aaf-112">cible : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d6aaf-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="d6aaf-113">Un registre Quantum encodant un entier non signé utilisant l’encodage Little-endian dans la base double (QFT).</span><span class="sxs-lookup"><span data-stu-id="d6aaf-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6aaf-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6aaf-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d6aaf-115">Notes</span><span class="sxs-lookup"><span data-stu-id="d6aaf-115">Remarks</span></span>

<span data-ttu-id="d6aaf-116">Notez que nous avons simplifié le circuit, car l’incrément est une constante classique, et non un registre Quantum.</span><span class="sxs-lookup"><span data-stu-id="d6aaf-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="d6aaf-117">Reportez-vous à la figure à la [ page 6 de arXiv : quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) pour le schéma du circuit et l’explication.</span><span class="sxs-lookup"><span data-stu-id="d6aaf-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="d6aaf-118">Références</span><span class="sxs-lookup"><span data-stu-id="d6aaf-118">References</span></span>

- [<span data-ttu-id="d6aaf-119">*Thomas G. Draper* , arXiv : quant-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="d6aaf-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="d6aaf-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6aaf-120">See Also</span></span>

- [<span data-ttu-id="d6aaf-121">Microsoft. Quantum. Arithmetic. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="d6aaf-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)