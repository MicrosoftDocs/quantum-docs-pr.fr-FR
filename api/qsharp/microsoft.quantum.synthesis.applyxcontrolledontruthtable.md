---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Opération ApplyXControlledOnTruthTable
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203295"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="9682b-102">Opération ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="9682b-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="9682b-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9682b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9682b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9682b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9682b-105">Applique l' @"microsoft.quantum.intrinsic.x" opération sur `target` , si la fonction booléenne `func` prend la valeur true pour l’assignation classique dans `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="9682b-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9682b-106">Description</span><span class="sxs-lookup"><span data-stu-id="9682b-106">Description</span></span>

<span data-ttu-id="9682b-107">L’opération implémente l’opération unitaire \begin{align} U\ket {x} \ Ket {y} = \ket{x}\ket{y \oplus f (x)} \end{align} où $x $ et $y $ représentent `controlRegister` et `target` , respectivement.</span><span class="sxs-lookup"><span data-stu-id="9682b-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="9682b-108">La fonction booléenne $f $ est représentée sous la forme d’un tableau de vérité dans le cadre d’un grand entier.</span><span class="sxs-lookup"><span data-stu-id="9682b-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="9682b-109">Par exemple, la fonction majoritaire sur trois entrées est représentée par le bitstring `11101000` , où le bit le plus significatif `1` correspond à l’assignation d’entrée `(1, 1, 1)` , et le bit le moins significatif `0` correspond à l’assignation d’entrée `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="9682b-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="9682b-110">Il peut être représenté par le grand entier `0xE8L` en notation hexadécimale ou comme en `232L` notation décimale.</span><span class="sxs-lookup"><span data-stu-id="9682b-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="9682b-111">Le `L` suffixe indique que la constante est de type `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="9682b-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="9682b-112">Vous trouverez plus d’informations sur cette représentation dans les [tables de vérité Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span><span class="sxs-lookup"><span data-stu-id="9682b-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="9682b-113">L’implémentation utilise des @"microsoft.quantum.intrinsic.cnot" portes et @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="9682b-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="9682b-114">Entrée</span><span class="sxs-lookup"><span data-stu-id="9682b-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="9682b-115">Func : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9682b-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9682b-116">Table de vérité booléenne représentée comme grand entier</span><span class="sxs-lookup"><span data-stu-id="9682b-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="9682b-117">controlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9682b-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9682b-118">Registre de contrôle qubits</span><span class="sxs-lookup"><span data-stu-id="9682b-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9682b-119">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9682b-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9682b-120">Qubit cible</span><span class="sxs-lookup"><span data-stu-id="9682b-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="9682b-121">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9682b-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="9682b-122">Références</span><span class="sxs-lookup"><span data-stu-id="9682b-122">References</span></span>

- [<span data-ttu-id="9682b-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv : quant-pH/0303063</span><span class="sxs-lookup"><span data-stu-id="9682b-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="9682b-124">*Mathias Soeken*, *Martin Roetteler*, arXiv : 2005.12310</span><span class="sxs-lookup"><span data-stu-id="9682b-124">*Mathias Soeken*, *Martin Roetteler*, arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="9682b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9682b-125">See Also</span></span>

- [<span data-ttu-id="9682b-126">Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="9682b-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)