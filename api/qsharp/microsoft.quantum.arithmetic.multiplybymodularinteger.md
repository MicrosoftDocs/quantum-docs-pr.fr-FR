---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Opération MultiplyByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706390"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="e331e-102">Opération MultiplyByModularInteger</span><span class="sxs-lookup"><span data-stu-id="e331e-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="e331e-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e331e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e331e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e331e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e331e-105">Effectue une multiplication modulaire par une constante entière sur un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="e331e-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="e331e-106">Description</span><span class="sxs-lookup"><span data-stu-id="e331e-106">Description</span></span>

<span data-ttu-id="e331e-107">Faites-nous part `modulus` de $N $ et `constMultiplier` de $a $.</span><span class="sxs-lookup"><span data-stu-id="e331e-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="e331e-108">Cette opération implémente ensuite une opération unitaire définie par le mappage suivant sur la base du calcul : $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ pour tous les $y $ entre $0 $ et $N-$1.</span><span class="sxs-lookup"><span data-stu-id="e331e-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="e331e-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="e331e-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="e331e-110">constMultiplier : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e331e-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e331e-111">Constante par laquelle le multiplicateur est multiplié.</span><span class="sxs-lookup"><span data-stu-id="e331e-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="e331e-112">Doit être co-prime au modulo.</span><span class="sxs-lookup"><span data-stu-id="e331e-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e331e-113">modulo : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e331e-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e331e-114">L’opération de multiplication est effectuée par Modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="e331e-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="e331e-115">multiplicateur : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e331e-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e331e-116">Nombre multiplié par une constante.</span><span class="sxs-lookup"><span data-stu-id="e331e-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="e331e-117">Il s’agit d’un tableau de qubits codant un entier au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="e331e-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e331e-118">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e331e-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e331e-119">Notes</span><span class="sxs-lookup"><span data-stu-id="e331e-119">Remarks</span></span>

- <span data-ttu-id="e331e-120">Pour le schéma du circuit et l’explication, voir la figure 7 à la [page 8 de arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="e331e-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="e331e-121">Cette opération correspond à U ₐ dans [arXiv : quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="e331e-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>