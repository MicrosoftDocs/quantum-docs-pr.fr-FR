---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Opération MultiplexOperationsBruteForceFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2a9bb083b121745bd556aac692d5dc85ffec3791
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703975"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="88f09-102">Opération MultiplexOperationsBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="88f09-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="88f09-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="88f09-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="88f09-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88f09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88f09-105">Applique une opération unitaire contrôlée par multiplication $U $ qui applique un $V unitaire _j $ lorsqu’il est contrôlé par le numéro d’État n-qubit $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="88f09-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="88f09-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="88f09-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="88f09-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="88f09-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="88f09-108">unitaryGenerator : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> t => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="88f09-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="88f09-109">Tuple où le premier élément `Int` est le nombre d’unités de $N $, et le deuxième élément `(Int -> ('T => () is Adj + Ctl))` est une fonction qui accepte un entier $j $ dans $ [0, N-1] $ et génère l’opération unitaire $V _J $.</span><span class="sxs-lookup"><span data-stu-id="88f09-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="88f09-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="88f09-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="88f09-111">$n Registre de contrôle $-qubit qui encode les États de nombre $ \ket{j} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="88f09-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="88f09-112">cible : 't</span><span class="sxs-lookup"><span data-stu-id="88f09-112">target : 'T</span></span>

<span data-ttu-id="88f09-113">Registre qubit générique sur lequel $V _j $ agit.</span><span class="sxs-lookup"><span data-stu-id="88f09-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88f09-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88f09-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="88f09-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="88f09-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="88f09-116">Peut</span><span class="sxs-lookup"><span data-stu-id="88f09-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="88f09-117">Notes</span><span class="sxs-lookup"><span data-stu-id="88f09-117">Remarks</span></span>

<span data-ttu-id="88f09-118">`coefficients` sera complété avec les éléments d’identité si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="88f09-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="88f09-119">Cette version est implémentée directement en effectuant une boucle sur les opérateurs unitaires contrôlés par n.</span><span class="sxs-lookup"><span data-stu-id="88f09-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>