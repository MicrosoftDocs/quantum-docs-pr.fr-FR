---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: b8eff9d207752213ccdf42a9ad80fefb2da07216
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708615"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="5f098-102">BlockEncodingReflectionByLCU fonction)</span><span class="sxs-lookup"><span data-stu-id="5f098-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="5f098-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5f098-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5f098-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5f098-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5f098-105">Encode un opérateur d’intérêt dans un `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="5f098-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="5f098-106">Cela crée une `BlockEncodingReflection` unité de $U = P\cdot V\cdot P ^ \dagger $ qui encode un opérateur $H = \ sum_ {j} | \ alpha_j | U_j $ d’intérêt qui est une combinaison linéaire de divisions.</span><span class="sxs-lookup"><span data-stu-id="5f098-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="5f098-107">En général, $P $ est une unité de préparation de l’État, telle que $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ et $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.</span><span class="sxs-lookup"><span data-stu-id="5f098-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="5f098-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="5f098-108">Input</span></span>

### <a name="statepreparation--qubit--unit-adj--ctl"></a><span data-ttu-id="5f098-109">statePreparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="5f098-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5f098-110">Un $P unitaire $ qui prépare un État cible.</span><span class="sxs-lookup"><span data-stu-id="5f098-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="5f098-111">sélecteur : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="5f098-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5f098-112">$V unitaire $ qui encode les unités de composants de $H $.</span><span class="sxs-lookup"><span data-stu-id="5f098-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="5f098-113">Sortie : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="5f098-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="5f098-114">Une unité de $U $ agissant conjointement sur les registres `a` et `s` qui encode le bloc $H $ et satisfait $U' ^ {-1} = U $.</span><span class="sxs-lookup"><span data-stu-id="5f098-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f098-115">Notes</span><span class="sxs-lookup"><span data-stu-id="5f098-115">Remarks</span></span>

<span data-ttu-id="5f098-116">Cette `BlockEncoding` implémentation lui attribue les propriétés d’un `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="5f098-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f098-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f098-117">See Also</span></span>

- [<span data-ttu-id="5f098-118">Microsoft. Quantum. simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="5f098-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="5f098-119">Microsoft. Quantum. simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="5f098-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)