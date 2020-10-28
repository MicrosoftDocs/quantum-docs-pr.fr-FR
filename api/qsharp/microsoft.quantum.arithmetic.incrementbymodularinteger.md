---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Opération IncrementByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707262"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="8217c-102">Opération IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="8217c-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="8217c-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8217c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8217c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8217c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8217c-105">Effectue un incrément modulaire d’un registre qubit à l’aide d’une constante entière.</span><span class="sxs-lookup"><span data-stu-id="8217c-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="8217c-106">Description</span><span class="sxs-lookup"><span data-stu-id="8217c-106">Description</span></span>

<span data-ttu-id="8217c-107">Faites-nous part `increment` de $a $, `modulus` de $N $ et de l’entier encodé dans `target` par $y $.</span><span class="sxs-lookup"><span data-stu-id="8217c-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="8217c-108">L’opération effectue ensuite la transformation suivante : \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} entiers sont encodés au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="8217c-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="8217c-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="8217c-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="8217c-110">incrément : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8217c-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8217c-111">Incrément entier $a $ à ajouter à $y $.</span><span class="sxs-lookup"><span data-stu-id="8217c-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="8217c-112">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8217c-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8217c-113">Entier $N $ mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="8217c-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="8217c-114">cible : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8217c-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8217c-115">Entier $y $ dans le `LittleEndian` format auquel `increment` $a $ est ajouté.</span><span class="sxs-lookup"><span data-stu-id="8217c-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8217c-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8217c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8217c-117">Notes</span><span class="sxs-lookup"><span data-stu-id="8217c-117">Remarks</span></span>

<span data-ttu-id="8217c-118">Suppose que la valeur initiale de Target est inférieure à $N $ et que l’incrément $a $ est inférieur à $N $.</span><span class="sxs-lookup"><span data-stu-id="8217c-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="8217c-119">Notez que <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implémente la même opération dans la `PhaseLittleEndian` base.</span><span class="sxs-lookup"><span data-stu-id="8217c-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="8217c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8217c-120">See Also</span></span>

- [<span data-ttu-id="8217c-121">Microsoft. Quantum. Arithmetic. IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="8217c-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)