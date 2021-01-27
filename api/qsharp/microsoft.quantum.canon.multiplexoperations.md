---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Opération MultiplexOperations
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 1cf483bb0d3b7cc43d271b65a2363fab95ff0f3b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852528"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="68a74-102">Opération MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="68a74-102">MultiplexOperations operation</span></span>

<span data-ttu-id="68a74-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="68a74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="68a74-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68a74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68a74-105">Applique un tableau d’opérations contrôlé par un tableau d’États de nombre.</span><span class="sxs-lookup"><span data-stu-id="68a74-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="68a74-106">Autrement dit, applique une opération unitaire contrôlée par multiplication $U $ qui applique une $V unitaire _j $ lorsqu’elle est contrôlée par $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="68a74-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="68a74-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="68a74-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="68a74-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="68a74-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="68a74-109">unités : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="68a74-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="68a74-110">Tableau allant jusqu’à $2 ^ n $ opérations unitaires.</span><span class="sxs-lookup"><span data-stu-id="68a74-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="68a74-111">Le $j $ th opération est indexé par le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="68a74-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="68a74-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="68a74-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="68a74-113">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="68a74-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="68a74-114">cible : 't</span><span class="sxs-lookup"><span data-stu-id="68a74-114">target : 'T</span></span>

<span data-ttu-id="68a74-115">Registre qubit générique sur lequel $V _j $ agit.</span><span class="sxs-lookup"><span data-stu-id="68a74-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="68a74-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="68a74-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="68a74-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="68a74-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68a74-118">Peut</span><span class="sxs-lookup"><span data-stu-id="68a74-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="68a74-119">Notes</span><span class="sxs-lookup"><span data-stu-id="68a74-119">Remarks</span></span>

<span data-ttu-id="68a74-120">`coefficients` sera complété avec les éléments d’identité si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="68a74-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="68a74-121">Cette implémentation utilise $n-$1 auxiliaire qubits.</span><span class="sxs-lookup"><span data-stu-id="68a74-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="68a74-122">Références</span><span class="sxs-lookup"><span data-stu-id="68a74-122">References</span></span>

- <span data-ttu-id="68a74-123">Vers la première simulation de Quantum avec accélération de Quantum Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="68a74-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>