---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Opération MultiplexOperationsFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2fde0bf391568f39128e6dca4b535aa6b78407c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703966"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="fbd7b-102">Opération MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="fbd7b-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="fbd7b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fbd7b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fbd7b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbd7b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbd7b-105">Applique une opération unitaire contrôlée par multiplication $U $ qui applique une $V unitaire _j $ lorsqu’elle est contrôlée par le numéro d’État n-qubit $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="fbd7b-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="fbd7b-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="fbd7b-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="fbd7b-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="fbd7b-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="fbd7b-108">unitaryGenerator : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> t => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="fbd7b-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="fbd7b-109">Tuple où le premier élément `Int` est le nombre d’unités de $N $, et le deuxième élément `(Int -> ('T => () is Adj + Ctl))` est une fonction qui accepte un entier $j $ dans $ [0, N-1] $ et génère l’opération unitaire $V _J $.</span><span class="sxs-lookup"><span data-stu-id="fbd7b-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="fbd7b-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fbd7b-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fbd7b-111">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="fbd7b-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="fbd7b-112">cible : 't</span><span class="sxs-lookup"><span data-stu-id="fbd7b-112">target : 'T</span></span>

<span data-ttu-id="fbd7b-113">Registre qubit générique sur lequel $V _j $ agit.</span><span class="sxs-lookup"><span data-stu-id="fbd7b-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbd7b-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbd7b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fbd7b-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="fbd7b-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fbd7b-116">Peut</span><span class="sxs-lookup"><span data-stu-id="fbd7b-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="fbd7b-117">Notes</span><span class="sxs-lookup"><span data-stu-id="fbd7b-117">Remarks</span></span>

<span data-ttu-id="fbd7b-118">`coefficients` sera complété avec les éléments d’identité si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="fbd7b-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="fbd7b-119">Cette implémentation utilise $n-$1 auxiliaire qubits.</span><span class="sxs-lookup"><span data-stu-id="fbd7b-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="fbd7b-120">Références</span><span class="sxs-lookup"><span data-stu-id="fbd7b-120">References</span></span>

- [<span data-ttu-id="fbd7b-121">*Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su* , arXiv : 1711.10980</span><span class="sxs-lookup"><span data-stu-id="fbd7b-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su* , arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)