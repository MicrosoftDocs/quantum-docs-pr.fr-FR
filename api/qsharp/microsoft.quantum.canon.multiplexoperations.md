---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Opération MultiplexOperations
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703981"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="c7207-102">Opération MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="c7207-102">MultiplexOperations operation</span></span>

<span data-ttu-id="c7207-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7207-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7207-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7207-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7207-105">Applique un tableau d’opérations contrôlé par un tableau d’États de nombre.</span><span class="sxs-lookup"><span data-stu-id="c7207-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="c7207-106">Autrement dit, applique une opération unitaire contrôlée par multiplication $U $ qui applique une $V unitaire _j $ lorsqu’elle est contrôlée par $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="c7207-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="c7207-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="c7207-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="c7207-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c7207-108">Input</span></span>

### <a name="unitaries--t--unit-adj--ctl"></a><span data-ttu-id="c7207-109">unités : 't [=> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL []</span><span class="sxs-lookup"><span data-stu-id="c7207-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="c7207-110">Tableau allant jusqu’à $2 ^ n $ opérations unitaires.</span><span class="sxs-lookup"><span data-stu-id="c7207-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="c7207-111">Le $j $ th opération est indexé par le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="c7207-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="c7207-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7207-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c7207-113">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="c7207-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="c7207-114">cible : 't</span><span class="sxs-lookup"><span data-stu-id="c7207-114">target : 'T</span></span>

<span data-ttu-id="c7207-115">Registre qubit générique sur lequel $V _j $ agit.</span><span class="sxs-lookup"><span data-stu-id="c7207-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7207-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7207-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c7207-117">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c7207-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c7207-118">Peut</span><span class="sxs-lookup"><span data-stu-id="c7207-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c7207-119">Notes</span><span class="sxs-lookup"><span data-stu-id="c7207-119">Remarks</span></span>

<span data-ttu-id="c7207-120">`coefficients` sera complété avec les éléments d’identité si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="c7207-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="c7207-121">Cette implémentation utilise $n-$1 auxiliaire qubits.</span><span class="sxs-lookup"><span data-stu-id="c7207-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="c7207-122">Références</span><span class="sxs-lookup"><span data-stu-id="c7207-122">References</span></span>

- <span data-ttu-id="c7207-123">Vers la première simulation de Quantum avec accélération de Quantum Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="c7207-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>