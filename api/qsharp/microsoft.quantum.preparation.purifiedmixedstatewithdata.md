---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854275"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="b8447-102">PurifiedMixedStateWithData fonction)</span><span class="sxs-lookup"><span data-stu-id="b8447-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="b8447-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b8447-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b8447-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8447-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8447-105">Retourne une opération qui prépare une purification d’un État mixte donné, associée à un registre qui représente une collection donnée de données.</span><span class="sxs-lookup"><span data-stu-id="b8447-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="b8447-106">Un « État mixte purifié avec des données » fait référence à un État sous la forme σI √ pi | i ⟩ | XI ⟩ | garbagei ⟩, où chaque XI est un bitstring codant des données supplémentaires associées au registre | i ⟩.</span><span class="sxs-lookup"><span data-stu-id="b8447-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="b8447-107"> https://arxiv.org/pdf/1805.03662.pdf?page=15Pour plus d’informations, consultez.</span><span class="sxs-lookup"><span data-stu-id="b8447-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="b8447-108">Description</span><span class="sxs-lookup"><span data-stu-id="b8447-108">Description</span></span>

<span data-ttu-id="b8447-109">Utilise la technique Quantum ROM pour représenter une matrice de densité donnée, en retournant cette représentation comme opération de préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="b8447-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="b8447-110">En particulier, étant donné une liste de $N $ coefficients $ \ alpha_j $ et un bitstring $ \vec{x}_j $ associé à chaque coefficient, cette fonction retourne une opération qui utilise la technique Quantum ROM pour préparer une approximation $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ de l’État mixte $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $ où chaque $p _j $ est une approximation du coefficient $ \ alpha_j $ de sorte que $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ pour chaque $j $.</span><span class="sxs-lookup"><span data-stu-id="b8447-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="b8447-111">En cas de réussite d’un registre d’index et d’un registre de garbage qubits, initialement à l’État $ \ket {0} \ket{00\cdots 0}, l’opération retournée prépare les deux registres dans la purification de $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $ de sorte que la réinitialisation et la désallocation du registre de nettoyage de la mémoire enregistrent la préparation souhaitée dans l’erreur cible $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="b8447-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="b8447-112">Entrée</span><span class="sxs-lookup"><span data-stu-id="b8447-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="b8447-113">targetError : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b8447-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b8447-114">L’erreur cible $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="b8447-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="b8447-115">coefficients : ([double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="b8447-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="b8447-116">Tableau de $N $ coefficients spécifiant la probabilité des États de base, ainsi que le bitstring $ \vec{x} _j $ associé à chaque coefficient.</span><span class="sxs-lookup"><span data-stu-id="b8447-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="b8447-117">Les nombres négatifs $-\ alpha_j $ seront traités comme étant positifs $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="b8447-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="b8447-118">Sortie : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="b8447-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="b8447-119">Opération qui prépare $ \tilde \rho $ comme une purification sur un index commun et un garbage Register.</span><span class="sxs-lookup"><span data-stu-id="b8447-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8447-120">Notes</span><span class="sxs-lookup"><span data-stu-id="b8447-120">Remarks</span></span>

<span data-ttu-id="b8447-121">Les coefficients fournis à cette opération sont normalisés après la norme 1, de sorte que les coefficients sont toujours considérés comme une distribution de probabilité catégorique valide.</span><span class="sxs-lookup"><span data-stu-id="b8447-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="b8447-122">Références</span><span class="sxs-lookup"><span data-stu-id="b8447-122">References</span></span>

- <span data-ttu-id="b8447-123">Encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pâle, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="b8447-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="b8447-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8447-124">See Also</span></span>

- [<span data-ttu-id="b8447-125">Microsoft. Quantum. PREPARATION. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="b8447-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)