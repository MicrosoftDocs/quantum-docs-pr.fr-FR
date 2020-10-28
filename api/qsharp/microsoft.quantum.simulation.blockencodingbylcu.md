---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709020"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="f2e62-102">BlockEncodingByLCU fonction)</span><span class="sxs-lookup"><span data-stu-id="f2e62-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="f2e62-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f2e62-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f2e62-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2e62-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f2e62-105">Encode un opérateur d’intérêt dans un `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="f2e62-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="f2e62-106">Cela crée une `BlockEncoding` unité de $U = P\cdot V\cdot P ^ \dagger $ qui encode un opérateur $H = \ sum_ {j} | \ alpha_j | U_j $ d’intérêt qui est une combinaison linéaire de divisions.</span><span class="sxs-lookup"><span data-stu-id="f2e62-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="f2e62-107">En règle générale, $P $ est une unité de préparation de l’État, telle que $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ et $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="f2e62-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f2e62-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="f2e62-108">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="f2e62-109">statePreparation : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="f2e62-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f2e62-110">Un $P unitaire $ qui prépare un État cible.</span><span class="sxs-lookup"><span data-stu-id="f2e62-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="f2e62-111">sélecteur : ('t, 's) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="f2e62-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f2e62-112">$V unitaire $ qui encode les unités de composants de $H $.</span><span class="sxs-lookup"><span data-stu-id="f2e62-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit-adj--ctl"></a><span data-ttu-id="f2e62-113">Sortie : ('t, ') => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="f2e62-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f2e62-114">Un $U unitaire $ agissant conjointement sur `a` les registres et `s` qui encodent les blocs $H $ et satisfont $U ^ \Dagger = U $.</span><span class="sxs-lookup"><span data-stu-id="f2e62-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f2e62-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="f2e62-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f2e62-116">Peut</span><span class="sxs-lookup"><span data-stu-id="f2e62-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="f2e62-117">Examin</span><span class="sxs-lookup"><span data-stu-id="f2e62-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="f2e62-118">Notes</span><span class="sxs-lookup"><span data-stu-id="f2e62-118">Remarks</span></span>

<span data-ttu-id="f2e62-119">Cette `BlockEncoding` implémentation lui attribue les propriétés d’un `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="f2e62-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2e62-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2e62-120">See Also</span></span>

- [<span data-ttu-id="f2e62-121">Microsoft. Quantum. simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="f2e62-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="f2e62-122">Microsoft. Quantum. simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="f2e62-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)