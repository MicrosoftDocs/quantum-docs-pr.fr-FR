---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Opération IncrementPhaseByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707235"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="8e849-102">Opération IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="8e849-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="8e849-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8e849-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8e849-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8e849-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8e849-105">Effectue un incrément modulaire d’un registre qubit à l’aide d’une constante entière.</span><span class="sxs-lookup"><span data-stu-id="8e849-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="8e849-106">Description</span><span class="sxs-lookup"><span data-stu-id="8e849-106">Description</span></span>

<span data-ttu-id="8e849-107">Faites-nous part `increment` de $a $, `modulus` de $N $ et de l’entier encodé dans `target` par $y $.</span><span class="sxs-lookup"><span data-stu-id="8e849-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="8e849-108">L’opération effectue ensuite la transformation suivante : \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} entiers sont encodés au format Little endian dans QFT.</span><span class="sxs-lookup"><span data-stu-id="8e849-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="8e849-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="8e849-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="8e849-110">incrément : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8e849-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8e849-111">Incrément entier $a $ à ajouter à $y $.</span><span class="sxs-lookup"><span data-stu-id="8e849-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="8e849-112">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8e849-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8e849-113">Entier $N $ mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="8e849-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="8e849-114">cible : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8e849-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="8e849-115">Entier $y $ dans un format Little-endian encodé en phase qui `increment` $a $ est ajouté à.</span><span class="sxs-lookup"><span data-stu-id="8e849-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e849-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e849-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8e849-117">Notes</span><span class="sxs-lookup"><span data-stu-id="8e849-117">Remarks</span></span>

<span data-ttu-id="8e849-118">Suppose que `target` a le bit le plus élevé défini sur 0.</span><span class="sxs-lookup"><span data-stu-id="8e849-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="8e849-119">Suppose également que la valeur de Target est inférieure à $N $.</span><span class="sxs-lookup"><span data-stu-id="8e849-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="8e849-120">Pour le schéma du circuit et l’explication, voir la figure 5 sur la [page 5 de arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="8e849-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="8e849-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e849-121">See Also</span></span>

- [<span data-ttu-id="8e849-122">Microsoft. Quantum. Arithmetic. IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="8e849-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)