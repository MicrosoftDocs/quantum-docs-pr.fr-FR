---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230019"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="88d36-102">PurifiedMixedState fonction)</span><span class="sxs-lookup"><span data-stu-id="88d36-102">PurifiedMixedState function</span></span>

<span data-ttu-id="88d36-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="88d36-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="88d36-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88d36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88d36-105">Retourne une opération qui prépare une purification d’un État mixte donné.</span><span class="sxs-lookup"><span data-stu-id="88d36-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="88d36-106">Un « État mixte purifié » fait référence aux États de la forme | ψ ⟩ = σI √ pi | i ⟩ | garbagei ⟩ spécifiés par un vecteur de coefficients {pi}.</span><span class="sxs-lookup"><span data-stu-id="88d36-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="88d36-107">Les États de ce formulaire peuvent être réduits à des États mixtes p ≔ pi | i ⟩ ⟨ i | en traçant sur le registre de « nettoyage » (autrement dit, un État mixte qui est diagonal dans la base de calcul).</span><span class="sxs-lookup"><span data-stu-id="88d36-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="88d36-108"> https://arxiv.org/pdf/1805.03662.pdf?page=15Pour plus d’informations, consultez.</span><span class="sxs-lookup"><span data-stu-id="88d36-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="88d36-109">Description</span><span class="sxs-lookup"><span data-stu-id="88d36-109">Description</span></span>

<span data-ttu-id="88d36-110">Utilise la technique Quantum ROM pour représenter une matrice de densité donnée, en retournant cette représentation comme opération de préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="88d36-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="88d36-111">En particulier, à partir d’une liste de $N $ coefficients $ \ alpha_j $, cette fonction retourne une opération qui utilise la technique Quantum ROM pour préparer une approximation $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ de l’État mixte $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $ où chaque $p _j $ est une approximation du coefficient $ \ alpha_j $ de sorte que $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ pour chaque $j $.</span><span class="sxs-lookup"><span data-stu-id="88d36-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="88d36-112">En cas de réussite d’un registre d’index et d’un registre de garbage qubits, initialement, dans l’État $ \ket {0} \ket{00\cdots 0}, l’opération retournée prépare les deux registres dans la purification de $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $, de telle sorte que la réinitialisation et la désallocation du registre de nettoyage de la mémoire enregistrent la préparation souhaitée</span><span class="sxs-lookup"><span data-stu-id="88d36-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="88d36-113">Entrée</span><span class="sxs-lookup"><span data-stu-id="88d36-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="88d36-114">targetError : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88d36-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88d36-115">L’erreur cible $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="88d36-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="88d36-116">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="88d36-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="88d36-117">Tableau de $N $ coefficient spécifiant la probabilité des États de base.</span><span class="sxs-lookup"><span data-stu-id="88d36-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="88d36-118">Les nombres négatifs $-\ alpha_j $ seront traités comme étant positifs $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="88d36-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="88d36-119">Sortie : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="88d36-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="88d36-120">Opération qui prépare $ \tilde \rho $ comme une purification sur un index commun et un garbage Register.</span><span class="sxs-lookup"><span data-stu-id="88d36-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="88d36-121">Notes</span><span class="sxs-lookup"><span data-stu-id="88d36-121">Remarks</span></span>

<span data-ttu-id="88d36-122">Les coefficients fournis à cette opération sont normalisés après la norme 1, de sorte que les coefficients sont toujours considérés comme une distribution de probabilité catégorique valide.</span><span class="sxs-lookup"><span data-stu-id="88d36-122">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="88d36-123">Références</span><span class="sxs-lookup"><span data-stu-id="88d36-123">References</span></span>

- <span data-ttu-id="88d36-124">Encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pâle, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="88d36-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="88d36-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88d36-125">See Also</span></span>

- [<span data-ttu-id="88d36-126">Microsoft. Quantum. PREPARATION. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="88d36-126">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)