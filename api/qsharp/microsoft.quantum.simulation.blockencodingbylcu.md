---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229543"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="68a97-102">BlockEncodingByLCU fonction)</span><span class="sxs-lookup"><span data-stu-id="68a97-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="68a97-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="68a97-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="68a97-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68a97-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68a97-105">Encode un opérateur d’intérêt dans un `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="68a97-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="68a97-106">Cela crée une `BlockEncoding` unité de $U = P\cdot V\cdot P ^ \dagger $ qui encode un opérateur $H = \ sum_ {j} | \ alpha_j | U_j $ d’intérêt qui est une combinaison linéaire de divisions.</span><span class="sxs-lookup"><span data-stu-id="68a97-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="68a97-107">En règle générale, $P $ est une unité de préparation de l’État, telle que $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ et $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="68a97-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="68a97-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="68a97-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="68a97-109">statePreparation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="68a97-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="68a97-110">Un $P unitaire $ qui prépare un État cible.</span><span class="sxs-lookup"><span data-stu-id="68a97-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="68a97-111">sélecteur : ('t, s) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="68a97-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="68a97-112">$V unitaire $ qui encode les unités de composants de $H $.</span><span class="sxs-lookup"><span data-stu-id="68a97-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="68a97-113">Sortie : ('t, ') => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="68a97-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="68a97-114">Un $U unitaire $ agissant conjointement sur `a` les registres et `s` qui encodent les blocs $H $ et satisfont $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="68a97-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="68a97-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="68a97-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68a97-116">Peut</span><span class="sxs-lookup"><span data-stu-id="68a97-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="68a97-117">Examin</span><span class="sxs-lookup"><span data-stu-id="68a97-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="68a97-118">Notes</span><span class="sxs-lookup"><span data-stu-id="68a97-118">Remarks</span></span>

<span data-ttu-id="68a97-119">Cette `BlockEncoding` implémentation lui attribue les propriétés d’un `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="68a97-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="68a97-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68a97-120">See Also</span></span>

- [<span data-ttu-id="68a97-121">Microsoft. Quantum. simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="68a97-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="68a97-122">Microsoft. Quantum. simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="68a97-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)