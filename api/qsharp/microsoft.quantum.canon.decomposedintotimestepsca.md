---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: e82df36d2e4f3767a152d5c92d7b1897c744a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840687"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="f4137-102">DecomposedIntoTimeStepsCA fonction)</span><span class="sxs-lookup"><span data-stu-id="f4137-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="f4137-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4137-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4137-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4137-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4137-105">Retourne une opération implémentant l’intégrateur Trotter – Suzuki pour une opération donnée.</span><span class="sxs-lookup"><span data-stu-id="f4137-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f4137-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="f4137-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="f4137-107">nSteps : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4137-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4137-108">Nombre d’opérations à décomposer en étapes horaires.</span><span class="sxs-lookup"><span data-stu-id="f4137-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="f4137-109">OP : ([int](xref:microsoft.quantum.lang-ref.int),[double](xref:microsoft.quantum.lang-ref.double), t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="f4137-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f4137-110">Opération qui accepte une entrée d’index (type `Int` ) et une entrée de temps (type `Double` ) pour la décomposition.</span><span class="sxs-lookup"><span data-stu-id="f4137-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="f4137-111">trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4137-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4137-112">Sélectionne l’ordre de l’intégrateur Trotter-Suzuki à utiliser.</span><span class="sxs-lookup"><span data-stu-id="f4137-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="f4137-113">Ordre 1 et même commandes 2, 4, 6,... sont actuellement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f4137-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="f4137-114">Sortie : ([double](xref:microsoft.quantum.lang-ref.double), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="f4137-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f4137-115">Retourne un qui implémente l’intégrateur Trotter – Suzuki, où le premier paramètre `Double` est la taille de l’étape d’intégration, et le deuxième paramètre est la cible sur laquelle agir.</span><span class="sxs-lookup"><span data-stu-id="f4137-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f4137-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="f4137-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4137-117">Peut</span><span class="sxs-lookup"><span data-stu-id="f4137-117">'T</span></span>

<span data-ttu-id="f4137-118">Type sur lequel chaque étape doit agir ; en général, `Qubit[]` ou `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="f4137-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4137-119">Notes</span><span class="sxs-lookup"><span data-stu-id="f4137-119">Remarks</span></span>

<span data-ttu-id="f4137-120">Quand `order` elle est appelée avec égal à `1` , cette fonction retourne une opération qui peut être simulée par l’intégrateur Trotter – Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ où nous avons suivi la notation de [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) et laissons à $ \lambda $ le temps d’évolution (représenté par la première entrée de l’opération renvoyée). et \{ que \} la valeur de $ H_j _ {j = 1} ^ {m} $ soit le jeu de générateurs dynamiques (skew-Hermitian) qui est intégré, ce qui `op(j, lambda, _)` est simulé par l’opérateur unitaire $e ^ {H_j \lambda} $.</span><span class="sxs-lookup"><span data-stu-id="f4137-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="f4137-121">De même, un `order` de `2` retourne l’Trotter symétrique de deuxième ordre, Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j' = m} ^ {1} e ^ {H_ {j'} \lambda/2}.</span><span class="sxs-lookup"><span data-stu-id="f4137-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="f4137-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f4137-122">\end{align} $$</span></span>

<span data-ttu-id="f4137-123">Les valeurs paires les plus élevées de `order` sont implémentées à l’aide de la construction récursive de [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="f4137-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="f4137-124">Références</span><span class="sxs-lookup"><span data-stu-id="f4137-124">References</span></span>

- [<span data-ttu-id="f4137-125">*D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="f4137-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)