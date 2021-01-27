---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Opération MultiplyByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846489"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="d7beb-102">Opération MultiplyByModularInteger</span><span class="sxs-lookup"><span data-stu-id="d7beb-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="d7beb-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d7beb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d7beb-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7beb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7beb-105">Effectue une multiplication modulaire par une constante entière sur un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="d7beb-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d7beb-106">Description</span><span class="sxs-lookup"><span data-stu-id="d7beb-106">Description</span></span>

<span data-ttu-id="d7beb-107">Faites-nous part `modulus` de $N $ et `constMultiplier` de $a $.</span><span class="sxs-lookup"><span data-stu-id="d7beb-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="d7beb-108">Cette opération implémente ensuite une opération unitaire définie par le mappage suivant sur la base du calcul : $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ pour tous les $y $ entre $0 $ et $N-$1.</span><span class="sxs-lookup"><span data-stu-id="d7beb-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="d7beb-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="d7beb-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="d7beb-110">constMultiplier : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7beb-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7beb-111">Constante par laquelle le multiplicateur est multiplié.</span><span class="sxs-lookup"><span data-stu-id="d7beb-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="d7beb-112">Doit être co-prime au modulo.</span><span class="sxs-lookup"><span data-stu-id="d7beb-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="d7beb-113">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7beb-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7beb-114">L’opération de multiplication est effectuée par Modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="d7beb-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="d7beb-115">multiplicateur : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d7beb-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d7beb-116">Nombre multiplié par une constante.</span><span class="sxs-lookup"><span data-stu-id="d7beb-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="d7beb-117">Il s’agit d’un tableau de qubits codant un entier au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="d7beb-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7beb-118">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7beb-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d7beb-119">Notes</span><span class="sxs-lookup"><span data-stu-id="d7beb-119">Remarks</span></span>

- <span data-ttu-id="d7beb-120">Pour le schéma du circuit et l’explication, voir la figure 7 à la [page 8 de arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="d7beb-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="d7beb-121">Cette opération correspond à U ₐ dans [arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="d7beb-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>