---
title: Simulation de Dynamics Hamilton | Microsoft Docs
description: Simulation de documents conceptuels de Dynamics
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 905b03478d453e475fc1e49ea5f88dd0cd2704bc
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184064"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="86abd-103">Simulation de Dynamics Hamilton</span><span class="sxs-lookup"><span data-stu-id="86abd-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="86abd-104">Une fois que le nom de la base de l’environnement Hamilton a été exprimé sous la forme d’une somme d’opérateurs élémentaires, la dynamique peut ensuite être compilée en opérations de porte fondamentale à l’aide d’un hôte de techniques bien connues.</span><span class="sxs-lookup"><span data-stu-id="86abd-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="86abd-105">Trois approches efficaces sont les suivantes : Trotter – Suzuki Formulas, Linear combinaisons of Units and qubitization.</span><span class="sxs-lookup"><span data-stu-id="86abd-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="86abd-106">Nous expliquons ces trois approches ci-dessous et proposons des exemples concrets de questions sur la façon d’implémenter ces méthodes à l’aide de la bibliothèque de simulation de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="86abd-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="86abd-107">Trotter – formules Suzuki</span><span class="sxs-lookup"><span data-stu-id="86abd-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="86abd-108">L’idée sous-jacente des formules Trotter – Suzuki est simple : Exprimez le sous-plan Hamilton comme une somme de Hamiltonians faciles à simuler, puis rapprochez l’évolution totale sous la forme d’une séquence de ces évolutions plus simples.</span><span class="sxs-lookup"><span data-stu-id="86abd-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="86abd-109">En particulier, laissez $H = \sum_{j = 1} ^ m H_j $ est le lieu de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="86abd-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="86abd-110">Puis, $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \prod_{j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, ce qui signifie que, si $t \ll $1, l’erreur de cette approximation devient négligeable.</span><span class="sxs-lookup"><span data-stu-id="86abd-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="86abd-111">Notez que si $e ^ {-i H t} $ étaient une valeur exponentielle ordinaire, l’erreur de cette approximation ne serait pas $O (m ^ 2 t ^ 2) $ : il s’agit de zéro.</span><span class="sxs-lookup"><span data-stu-id="86abd-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="86abd-112">Cette erreur se produit parce que $e ^ {-iHt} $ est un opérateur exponentiel et, par conséquent, une erreur est survenue lors de l’utilisation de cette formule en raison du fait que les $H $ Terms _J $ ne sont pas inactives (par*exemple*, $H _J H_k \Ne H_k H_j $ en général).</span><span class="sxs-lookup"><span data-stu-id="86abd-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="86abd-113">Si $t $ est large, les formules Trotter – Suzuki peuvent toujours être utilisées pour simuler la dynamique avec précision en la fractionnant en une séquence d’étapes courtes.</span><span class="sxs-lookup"><span data-stu-id="86abd-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="86abd-114">Laissez $r $ le nombre d’étapes prises dans l’évolution du temps.</span><span class="sxs-lookup"><span data-stu-id="86abd-114">Let $r$ be the number of steps taken in the time evolution.</span></span>
<span data-ttu-id="86abd-115">Ensuite, nous disposons de $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \left (\prod_{j = 1} ^ m e ^ {-iH_j t/r} \ Right) ^ r + O (m ^ 2 t ^ 2/r). $ $, ce qui signifie que si $r $ se met à l’échelle comme $m ^ 2 t ^ 2/\ Epsilon $, l’erreur peut être effectuée au plus $ \epsilon $ pour n’importe quel $ \epsilon > 0 $.</span><span class="sxs-lookup"><span data-stu-id="86abd-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="86abd-116">Des approximations plus précises peuvent être générées en construisant une séquence de exponentiels d’opérateur de façon à ce que les termes d’erreur s’annulent.</span><span class="sxs-lookup"><span data-stu-id="86abd-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="86abd-117">La formule la plus simple, la formule Trotter symétrique ou le fractionnement Strang, prend la forme $ $ U_1 (t) = \prod_{j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3), $ $, qui peut être inférieur à $ \epsilon $ pour n’importe quel $ \epsilon > 0 $ en choisissant $ r $ à mettre à l’échelle en tant que $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.</span><span class="sxs-lookup"><span data-stu-id="86abd-117">The simplest such formula, the symmetric Trotter formula or Strang splitting, takes the form $$ U_1(t) =\prod_{j=1}^m e^{-iH_j t/2}\prod_{j=m}^1 e^{-iH_j t} = e^{-iHt} + O(m^3 t^3), $$ which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="86abd-118">Même les formules Trotter d’ordre supérieur peuvent être construites sur la base de $U _ 1 $.</span><span class="sxs-lookup"><span data-stu-id="86abd-118">Even higher-order Trotter formulas can be constructed based on $U_1$.</span></span>
<span data-ttu-id="86abd-119">La plus simple est la formule de quatrième ordre suivante : initialement introduit par Suzuki : $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5t ^ 5), $ $ where $s _ 1 = (4-4 ^ {1/3}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="86abd-119">The simplest is the following fourth order formula, originally introduced by Suzuki: $$ U_2(t) = U_1^2(s_1t) U_1([1-4s_1]t)U_1^2(s_1 t) = e^{-iHt} +O(m^5t^5), $$ where $s_1 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="86abd-120">En général, les formules de poids fort arbitraires peuvent être construites de la même façon ; Toutefois, les coûts engendrés par l’utilisation d’intégrateurs plus complexes compensent souvent les avantages supérieurs au quatrième ordre pour les problèmes les plus pratiques.</span><span class="sxs-lookup"><span data-stu-id="86abd-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="86abd-121">Pour que les stratégies ci-dessus fonctionnent, nous avons besoin d’une méthode pour simuler une classe étendue de $e ^ {-iH_j t} $.</span><span class="sxs-lookup"><span data-stu-id="86abd-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="86abd-122">La famille de Hamiltonians la plus simple, et sans doute la plus utile, que nous pourrions utiliser ici sont les opérateurs Pauli.</span><span class="sxs-lookup"><span data-stu-id="86abd-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="86abd-123">Les opérateurs Pauli peuvent être facilement simulés, car ils peuvent être diagonés à l’aide d’opérations Clifford (qui sont des portes standard dans Quantum Computing).</span><span class="sxs-lookup"><span data-stu-id="86abd-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="86abd-124">De plus, une fois qu’ils ont été mis en diagonale, leur valeurs propres peut être trouvé en calculant la parité du qubits sur lequel ils agissent.</span><span class="sxs-lookup"><span data-stu-id="86abd-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="86abd-125">Par exemple, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ où $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="86abd-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="86abd-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="86abd-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="86abd-127">0 & 0 & e ^ {IT} & 0 </span><span class="sxs-lookup"><span data-stu-id="86abd-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="86abd-128">0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="86abd-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="86abd-129">$ $ Here, $e ^ {-iHt} \ket{00} = e ^ {IT} \ket{00}$ et $e ^ {-iHt} \ket{01} = e ^ {-IT} \ket{01}$, ce qui peut être vu directement par le fait que la parité de $0 $ est $0 $, tandis que la parité de la chaîne de bits $1 $ est $1 $.</span><span class="sxs-lookup"><span data-stu-id="86abd-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="86abd-130">Les exponentiels des opérateurs Pauli peuvent être implémentés directement dans Q # à l’aide de l’opération <xref:microsoft.quantum.primitive.exp> :</span><span class="sxs-lookup"><span data-stu-id="86abd-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.primitive.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="86abd-131">Pour Fermionic Hamiltonians, la [décomposition de Jordanie – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) mappe facilement le sein de la Communauté au sein d’une somme d’opérateurs Pauli.</span><span class="sxs-lookup"><span data-stu-id="86abd-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="86abd-132">Cela signifie que l’approche ci-dessus peut facilement être adaptée pour simuler la chimie.</span><span class="sxs-lookup"><span data-stu-id="86abd-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="86abd-133">Au lieu de boucler manuellement sur tous les termes de Pauli dans la représentation Jordanie-Wigner, vous trouverez ci-dessous un exemple simple de la façon dont l’exécution d’une telle simulation dans la chimie.</span><span class="sxs-lookup"><span data-stu-id="86abd-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="86abd-134">Notre point de départ est un [encodage de Jordanie – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) du Fermionic Hamilton, exprimé en code en tant qu’instance de la classe `JordanWignerEncoding`.</span><span class="sxs-lookup"><span data-stu-id="86abd-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="86abd-135">Ce format de la Jordanie – Wigner reprsentation qui est consommable par les algorithmes de simulation Q # est un type défini par l’utilisateur `JordanWignerEncodingData`.</span><span class="sxs-lookup"><span data-stu-id="86abd-135">This format of the Jordan–Wigner reprsentation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="86abd-136">Dans Q #, ce format est passé à une fonction pratique `TrotterStepOracle` qui retourne un opérateur d’évolution du temps à l’aide de l’intégrateur Trotter — Suzuki, en plus des autres paramètres requis pour son exécution.</span><span class="sxs-lookup"><span data-stu-id="86abd-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="86abd-137">Plus important encore, cette implémentation applique des optimisations présentées dans [simulation de la structure électronique Hamiltonians à l’aide d’ordinateurs quantiques et l'](https://arxiv.org/abs/1001.3855) [amélioration des algorithmes quantiques pour la chimie quantique](https://arxiv.org/abs/1403.1539) afin de réduire le nombre de les rotations à qubit unique sont requises, ainsi que la réduction des erreurs de simulation.</span><span class="sxs-lookup"><span data-stu-id="86abd-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="86abd-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="86abd-138">Qubitization</span></span>

<span data-ttu-id="86abd-139">Qubitization est une autre approche de la simulation qui utilise des idées de parcours quantiques pour simuler la dynamique quantique.</span><span class="sxs-lookup"><span data-stu-id="86abd-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="86abd-140">Bien que qubitization requière plus de qubits de formules Trotter, la méthode promet une mise à l’échelle optimale avec l’heure d’évolution et la tolérance d’erreur.</span><span class="sxs-lookup"><span data-stu-id="86abd-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="86abd-141">Pour ces raisons, il s’agit d’une méthode privilégiée pour simuler la dynamique de la Hamilton en général et pour résoudre le problème de structure électronique en particulier.</span><span class="sxs-lookup"><span data-stu-id="86abd-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="86abd-142">À un niveau élevé, qubitization effectue les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="86abd-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="86abd-143">Tout d’abord, laissez $H = \sum_j h_j H_j $ pour Unity et Hermitian $H _J $ et $h _J \ GE $0.</span><span class="sxs-lookup"><span data-stu-id="86abd-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="86abd-144">En exécutant une paire de réflexions, qubitization implémente un opérateur qui est équivalent à $ $W = e ^ {\pm i \cos ^{-1}(H/| h | _ 1)}, $ $ where $ | H | _ 1 = \sum_j | h_j | $.</span><span class="sxs-lookup"><span data-stu-id="86abd-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="86abd-145">L’étape suivante consiste à transformer le valeurs propres de l’opérateur de parcours de $e ^ {i\pm \cos ^{-1}(E_k/| h | _ 1)} $, où $E _K $ est le valeurs propres de $H $ à $e ^ {-iE_k t} $.</span><span class="sxs-lookup"><span data-stu-id="86abd-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="86abd-146">Pour ce faire, vous pouvez utiliser une variété de méthodes de transformation de valeur singulière Quantum, notamment le [traitement des signaux quantiques](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span><span class="sxs-lookup"><span data-stu-id="86abd-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="86abd-147">En guise d’alternative, si seules des quantités statiques sont souhaitées (par exemple, l’énergie de l’état du sol de la région Hamilton), il suffit d’appliquer l' [estimation de phase](xref:microsoft.quantum.libraries.characterization) directement à $W $ pour estimer l’énergie de l’état du sol en utilisant le cosinus du résultat.</span><span class="sxs-lookup"><span data-stu-id="86abd-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="86abd-148">Cela est important, car elle permet à la transformation spectrale d’être exécutée de manière classique plutôt que d’utiliser une méthode de transformation de valeur singulière quantique.</span><span class="sxs-lookup"><span data-stu-id="86abd-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="86abd-149">À un niveau plus détaillé, l’implémentation de qubitization nécessite deux sous-routines qui fournissent les interfaces pour le niveau de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="86abd-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="86abd-150">Contrairement aux méthodes Trotter – Suzuki, ces sous-routines sont Quantum not Classic et leur implémentation nécessite l’utilisation d’un plus grand nombre de qubits que nécessaire pour une simulation basée sur trotter.</span><span class="sxs-lookup"><span data-stu-id="86abd-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="86abd-151">La première sous-routine Quantum utilisée par qubitization est appelée $ \operatorname{Select} $ et elle est prévue pour yield \begin{Equation} \operatorname{Select} \ket{j} \ket{\Psi} = \ket{j} H_j \ket{\Psi}, \end{Equation} où chaque $H _J $ est supposé être Hermitian et unitaires.</span><span class="sxs-lookup"><span data-stu-id="86abd-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="86abd-152">Bien que cela puisse paraître restrictif, rappelez-vous que les opérateurs Pauli sont Hermitian et unitaires, de sorte que les applications telles que la simulation de la chimie quantique tombent naturellement dans cette infrastructure.</span><span class="sxs-lookup"><span data-stu-id="86abd-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="86abd-153">L’opération $ \operatorname{Select} $, peut-être étonnamment, est en fait une opération de réflexion.</span><span class="sxs-lookup"><span data-stu-id="86abd-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="86abd-154">Cela peut être vu par le fait que $ \operatorname{Select} ^ 2 \ Ket {j} \ket{\Psi} = \ket{j} \ket{\Psi} $ étant donné que chaque $H _J $ est unitaire et Hermitian et a donc valeurs propres $ \pm $1.</span><span class="sxs-lookup"><span data-stu-id="86abd-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="86abd-155">La deuxième sous-routine est appelée $ \operatorname{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="86abd-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="86abd-156">Tandis que l’opération Select fournit un moyen d’accéder de façon cohérente à chacun des $H termes de la _J $ la sous-routine prepare donne une méthode d’accès aux coefficients $h _J $, \begin{Equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{ | h | _ 1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="86abd-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="86abd-157">\end{Equation} ensuite, en utilisant une porte de phase contrôlée par multiplication, nous voyons que $ $ \Lambda\ket{0}^ {\otimes n} = \begin{cases} \-\ket{x} & \text{If} x = 0 </span><span class="sxs-lookup"><span data-stu-id="86abd-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="86abd-158">\ket{x} & \text{otherwise} \end{cases}.</span><span class="sxs-lookup"><span data-stu-id="86abd-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="86abd-159">L’opération $ \operatorname{Prepare} $ n’est pas utilisée directement dans qubitization, mais elle est utilisée pour implémenter une réflexion à propos de l’état que $ \operatorname{Prepare} $ crée $ $ \begin{align} R &amp; = 1-2 \ operatorName {prepare} \ket{0}\bra @no_ _t_2_ \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.</span><span class="sxs-lookup"><span data-stu-id="86abd-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="86abd-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="86abd-160">\end{align} $$</span></span>

<span data-ttu-id="86abd-161">L’opérateur de parcours, $W $, peut être exprimé en termes de $ \operatorname{Select} $ et $R $ Operations en tant que $ $ W = \operatorname{Select} R, $ $ qui peut encore être vu pour implémenter un opérateur équivalent (jusqu’à une isométrie) à $e ^ {\pm i \cos ^{-1}(H/| h | _ 1)} $.</span><span class="sxs-lookup"><span data-stu-id="86abd-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="86abd-162">Ces sous-routines sont faciles à configurer dans Q #.</span><span class="sxs-lookup"><span data-stu-id="86abd-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="86abd-163">À titre d’exemple, considérez le simple qubit transversal-Ising Hamilton où $H = X_1 + X_2 + Z_1 Z_2 $.</span><span class="sxs-lookup"><span data-stu-id="86abd-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="86abd-164">Dans ce cas, Q # code qui implémenterait l’opération $ \operatorname{Select} $ est appelé par <xref:microsoft.quantum.canon.multiplexoperations>, tandis que l’opération $ \operatorname{Prepare} $ peut être implémentée à l’aide de <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span><span class="sxs-lookup"><span data-stu-id="86abd-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="86abd-165">Vous trouverez un exemple qui implique de simuler le modèle Hubbard en tant qu' [exemple Q #](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).</span><span class="sxs-lookup"><span data-stu-id="86abd-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).</span></span>

<span data-ttu-id="86abd-166">La spécification manuelle de ces étapes pour les problèmes de chimie arbitraire nécessiterait un effort considérable, ce qui est évité à l’aide de la bibliothèque chimie.</span><span class="sxs-lookup"><span data-stu-id="86abd-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="86abd-167">À l’instar de l’algorithme de simulation Trotter – Suzuki ci-dessus, le `JordanWignerEncodingData` est passé à la fonction pratique `QubitizationOracle` qui retourne l’opérateur de parcours, en plus des autres paramètres requis pour son exécution.</span><span class="sxs-lookup"><span data-stu-id="86abd-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="86abd-168">Plus important encore, l’implémentation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> s’applique aux Hamiltonians arbitraires spécifiés comme une combinaison linéaire de chaînes Pauli.</span><span class="sxs-lookup"><span data-stu-id="86abd-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="86abd-169">Une version optimisée pour les simulations de chimie est appelée à l’aide de <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span><span class="sxs-lookup"><span data-stu-id="86abd-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="86abd-170">Cette version est optimisée pour réduire le nombre de grilles T à l’aide de techniques décrites dans [encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire](https://arxiv.org/abs/1805.03662).</span><span class="sxs-lookup"><span data-stu-id="86abd-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
