---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Opération IncrementPhaseByInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843147"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="e012c-102">Opération IncrementPhaseByInteger</span><span class="sxs-lookup"><span data-stu-id="e012c-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="e012c-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e012c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e012c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e012c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e012c-105">Incrémente un registre quantique non signé par un entier classique, à l’aide de rotations de phase.</span><span class="sxs-lookup"><span data-stu-id="e012c-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e012c-106">Description</span><span class="sxs-lookup"><span data-stu-id="e012c-106">Description</span></span>

<span data-ttu-id="e012c-107">Supposons que `target` encode un entier non signé $x $ dans un encodage Little endian et qu' `increment` il est égal à $a $.</span><span class="sxs-lookup"><span data-stu-id="e012c-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="e012c-108">Ensuite, cette opération implémente l’unité $ \ket{x} \mapsto \ket{x + a} $, où l’ajout est effectué modulo $2 ^ n $, où $n = \texttt{Length (target !)} $.</span><span class="sxs-lookup"><span data-stu-id="e012c-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="e012c-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="e012c-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="e012c-110">incrément : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e012c-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e012c-111">Entier par lequel `target` est incrémenté.</span><span class="sxs-lookup"><span data-stu-id="e012c-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="e012c-112">cible : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e012c-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e012c-113">Un registre Quantum encodant un entier non signé utilisant l’encodage Little-endian dans la base double (QFT).</span><span class="sxs-lookup"><span data-stu-id="e012c-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e012c-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e012c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e012c-115">Notes</span><span class="sxs-lookup"><span data-stu-id="e012c-115">Remarks</span></span>

<span data-ttu-id="e012c-116">Notez que nous avons simplifié le circuit, car l’incrément est une constante classique, et non un registre Quantum.</span><span class="sxs-lookup"><span data-stu-id="e012c-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="e012c-117">Reportez-vous à la figure à la [ page 6 de arXiv : quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) pour le schéma du circuit et l’explication.</span><span class="sxs-lookup"><span data-stu-id="e012c-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="e012c-118">Références</span><span class="sxs-lookup"><span data-stu-id="e012c-118">References</span></span>

- [<span data-ttu-id="e012c-119">*Thomas G. Draper*, arXiv : quant-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="e012c-119"> *Thomas G. Draper*, arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="e012c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e012c-120">See Also</span></span>

- [<span data-ttu-id="e012c-121">Microsoft. Quantum. Arithmetic. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="e012c-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)