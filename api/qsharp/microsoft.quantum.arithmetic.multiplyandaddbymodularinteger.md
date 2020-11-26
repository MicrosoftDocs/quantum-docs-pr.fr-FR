---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Opération MultiplyAndAddByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 169326879919b5b72d600c33d624776b720cc6bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222590"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="baf59-102">Opération MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="baf59-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="baf59-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="baf59-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="baf59-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="baf59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="baf59-105">Effectue une multiplication et un ajout modulaires par des constantes entières sur un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="baf59-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="baf59-106">Description</span><span class="sxs-lookup"><span data-stu-id="baf59-106">Description</span></span>

<span data-ttu-id="baf59-107">Implémente le mappage $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ pour un modulo donné $N $, multiplicateur de constante $a $ et opérande $y $.</span><span class="sxs-lookup"><span data-stu-id="baf59-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="baf59-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="baf59-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="baf59-109">constMultiplier : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="baf59-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="baf59-110">Entier $a $ à ajouter à chaque étiquette d’état de base.</span><span class="sxs-lookup"><span data-stu-id="baf59-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="baf59-111">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="baf59-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="baf59-112">Le modulo $N $, que l’addition et la multiplication sont prises en ce qui concerne.</span><span class="sxs-lookup"><span data-stu-id="baf59-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="baf59-113">multiplicateur : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="baf59-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="baf59-114">Registre quantique qui représente un entier non signé dont la valeur doit être ajoutée à chaque étiquette d’état de base de `summand` .</span><span class="sxs-lookup"><span data-stu-id="baf59-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="baf59-115">opérande : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="baf59-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="baf59-116">Registre quantique qui représente un entier non signé à utiliser comme cible pour cette opération.</span><span class="sxs-lookup"><span data-stu-id="baf59-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="baf59-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="baf59-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="baf59-118">Notes</span><span class="sxs-lookup"><span data-stu-id="baf59-118">Remarks</span></span>

- <span data-ttu-id="baf59-119">Pour le schéma du circuit et l’explication, voir la figure 6 à la [page 7 de arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="baf59-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="baf59-120">Cette opération correspond à CMULT (a) MOD (N) dans [arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="baf59-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="baf59-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="baf59-121">See Also</span></span>

- [<span data-ttu-id="baf59-122">Microsoft. Quantum. Arithmetic. MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="baf59-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)