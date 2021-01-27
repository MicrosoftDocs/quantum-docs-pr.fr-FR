---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Opération MultiplexOperationsBruteForceFromGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 395102c7ffffa81d1a9b6cbf29c9cc22fae6057e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852517"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="6d071-102">Opération MultiplexOperationsBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="6d071-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="6d071-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6d071-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6d071-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d071-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d071-105">Applique une opération unitaire contrôlée par multiplication $U $ qui applique un $V unitaire _j $ lorsqu’il est contrôlé par le numéro d’État n-qubit $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="6d071-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="6d071-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="6d071-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6d071-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="6d071-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="6d071-108">unitaryGenerator : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="6d071-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="6d071-109">Tuple où le premier élément `Int` est le nombre d’unités de $N $, et le deuxième élément `(Int -> ('T => () is Adj + Ctl))` est une fonction qui accepte un entier $j $ dans $ [0, N-1] $ et génère l’opération unitaire $V _J $.</span><span class="sxs-lookup"><span data-stu-id="6d071-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="6d071-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6d071-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6d071-111">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="6d071-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="6d071-112">cible : 't</span><span class="sxs-lookup"><span data-stu-id="6d071-112">target : 'T</span></span>

<span data-ttu-id="6d071-113">Registre qubit générique sur lequel $V _j $ agit.</span><span class="sxs-lookup"><span data-stu-id="6d071-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6d071-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d071-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6d071-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6d071-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6d071-116">Peut</span><span class="sxs-lookup"><span data-stu-id="6d071-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6d071-117">Notes</span><span class="sxs-lookup"><span data-stu-id="6d071-117">Remarks</span></span>

<span data-ttu-id="6d071-118">`coefficients` sera complété avec les éléments d’identité si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="6d071-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="6d071-119">Cette version est implémentée directement en effectuant une boucle sur les opérateurs unitaires contrôlés par n.</span><span class="sxs-lookup"><span data-stu-id="6d071-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>