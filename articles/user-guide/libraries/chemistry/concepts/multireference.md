---
title: Fonctions d’onde corrélées
description: Découvrez les corrélations dynamiques et non dynamiques dans wavefunctions à l’aide de la bibliothèque Microsoft Quantum chimie.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275092"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="c2476-103">Fonctions d’onde corrélées</span><span class="sxs-lookup"><span data-stu-id="c2476-103">Correlated wavefunctions</span></span>

<span data-ttu-id="c2476-104">Pour de nombreux systèmes, en particulier ceux proches de la géométrie d’équilibre, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) théorie fournit une description qualitative des propriétés moléculaires à l’aide d’un état de référence unique déterminant.</span><span class="sxs-lookup"><span data-stu-id="c2476-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="c2476-105">Toutefois, pour obtenir une précision quantitative, vous devez également prendre en compte les effets de corrélation.</span><span class="sxs-lookup"><span data-stu-id="c2476-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="c2476-106">Dans ce contexte, il est important de dinstinguish entre les corrélations dynamiques et non dynamiques.</span><span class="sxs-lookup"><span data-stu-id="c2476-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="c2476-107">Les corrélations dynamiques proviennent de la tendance des électrons à rester séparés, par exemple en raison d’une répulsion interélectronique.</span><span class="sxs-lookup"><span data-stu-id="c2476-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="c2476-108">Cet effet peut être modelé en tenant compte des informations de l’état de référence des électrons.</span><span class="sxs-lookup"><span data-stu-id="c2476-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="c2476-109">Des corrélations non dynamiques surviennent lorsque le wavefunction est dominé par deux configurations ou plus dans l’ordre avant toute chose, même pour obtenir uniquement une description qualitative du système.</span><span class="sxs-lookup"><span data-stu-id="c2476-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="c2476-110">Cela nécessite une superposition de déterminants et est un exemple de wavefunction à références multiréférence.</span><span class="sxs-lookup"><span data-stu-id="c2476-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="c2476-111">La bibliothèque chimie offre un moyen de spécifier un wavefunction de commande avant toute chose pour le problème de multiréférence comme superposition de déterminants.</span><span class="sxs-lookup"><span data-stu-id="c2476-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="c2476-112">Cette approche, que nous appelons les wavefunctionss à plusieurs références éparses, est efficace lorsque seuls quelques composants suffisent à spécifier la superposition.</span><span class="sxs-lookup"><span data-stu-id="c2476-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="c2476-113">La bibliothèque fournit également une méthode pour inclure des corrélations dynamiques sur une référence déterminante à l’aide de l’Ansatz d’unités généralisées de clusters couplés.</span><span class="sxs-lookup"><span data-stu-id="c2476-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="c2476-114">En outre, il construit également des circuits quantiques qui génèrent ces États sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="c2476-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="c2476-115">Ces États peuvent être spécifiés dans le [schéma Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), et nous fournissons également les fonctionnalités permettant de spécifier manuellement ces États via la bibliothèque chimie.</span><span class="sxs-lookup"><span data-stu-id="c2476-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="c2476-116">Wavefunction multi-Reference épars</span><span class="sxs-lookup"><span data-stu-id="c2476-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="c2476-117">Un État à plusieurs références $ \ket{\ psi_ {\rm {MCSCF}}} $ peut être spécifié explicitement comme une combinaison linéaire de $N le determininants $-Electron Slater.</span><span class="sxs-lookup"><span data-stu-id="c2476-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="c2476-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="c2476-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="c2476-119">\end{align} par exemple, l’État $ \propto (0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ peut être spécifié dans la bibliothèque chimie comme suit.</span><span class="sxs-lookup"><span data-stu-id="c2476-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
<span data-ttu-id="c2476-120">Cette représentation explicite des composants de superposition est effective lorsque seuls quelques composants doivent être spécifiés.</span><span class="sxs-lookup"><span data-stu-id="c2476-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="c2476-121">Il convient d’éviter d’utiliser cette représentation quand de nombreux composants sont requis pour capturer avec précision l’état souhaité.</span><span class="sxs-lookup"><span data-stu-id="c2476-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="c2476-122">La raison est le coût de la porte du circuit Quantum qui prépare cet État sur un ordinateur quantique, qui met à l’échelle de façon linéaire avec le nombre de composants superposition, et au plus augmentera avec la norme unidimensionnelle des amplitudes de superposition.</span><span class="sxs-lookup"><span data-stu-id="c2476-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="c2476-123">Wavefunction de clusters couplés unitaires</span><span class="sxs-lookup"><span data-stu-id="c2476-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="c2476-124">Il est également possible de spécifier une wavefunction de clusters à \ket{\ d’unités $ psi_ {\rm {UCC}}} $ à l’aide de la bibliothèque chemistery.</span><span class="sxs-lookup"><span data-stu-id="c2476-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="c2476-125">Dans ce cas, nous avons un état de référence unique déterminant, par exemple, $ \ket{\ psi_ {\rm{SCF}}} $.</span><span class="sxs-lookup"><span data-stu-id="c2476-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="c2476-126">Les composants des wavefunction de clusters à couplage unitaire sont ensuite spécifiés implicitement via un opérateur unitaire agissant sur un état de référence.</span><span class="sxs-lookup"><span data-stu-id="c2476-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="c2476-127">Cet opérateur Unity est couramment écrit sous la forme $e ^ {T-T ^ \dagger} $, où $T-T ^ \dagger $ est l’opérateur de cluster anti-Hermitian.</span><span class="sxs-lookup"><span data-stu-id="c2476-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="c2476-128">Par conséquent \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.</span><span class="sxs-lookup"><span data-stu-id="c2476-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="c2476-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c2476-129">\end{align}</span></span>

<span data-ttu-id="c2476-130">Il est également courant de fractionner l’opérateur de cluster $T = T_1 + T_2 + \cdots $ en parties, où chaque partie $T _j $ contient $j termes $ Body.</span><span class="sxs-lookup"><span data-stu-id="c2476-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="c2476-131">Dans la théorie généralisée de clusters couplés, l’opérateur de cluster à un corps (Single) se présente sous la forme \begin{align} T_1 = \ sum_ {PQ} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="c2476-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="c2476-132">et l’opérateur de cluster à deux corps (double) se présente sous la forme \begin{align} T_2 = \ sum_ {PQRS} T ^ {PQ} _ {RS} a ^ \ dagger_p un ^ \ dagger_q a_r A_S.</span><span class="sxs-lookup"><span data-stu-id="c2476-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="c2476-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c2476-133">\end{align}</span></span>

<span data-ttu-id="c2476-134">Des conditions d’ordre supérieur (triples, quadruples, etc.) sont possibles, mais ne sont pas actuellement prises en charge par la bibliothèque chimie.</span><span class="sxs-lookup"><span data-stu-id="c2476-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="c2476-135">Par exemple, laissez $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} $ et laissez $T = 0,123 a ^ \ dagger_0 A_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 A_1 a_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $.</span><span class="sxs-lookup"><span data-stu-id="c2476-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="c2476-136">Ensuite, cet État est instancié dans la bibliothèque chimie comme suit.</span><span class="sxs-lookup"><span data-stu-id="c2476-136">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

<span data-ttu-id="c2476-137">La sélection de spin convervation peut être rendue explicite en spécifiant `SpinOrbital` des index au lieu d’indices d’entiers.</span><span class="sxs-lookup"><span data-stu-id="c2476-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="c2476-138">Par exemple, laissez $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ et laissez $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ is spin convserving.</span><span class="sxs-lookup"><span data-stu-id="c2476-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="c2476-139">Ensuite, cet État est instancié dans la bibliothèque chimie comme suit.</span><span class="sxs-lookup"><span data-stu-id="c2476-139">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="c2476-140">Nous fournissons également une fonction pratique qui énumère tous les opérateurs de cluster de basculement qui Annihilate uniquement les spin-Orbits occupés et excitent uniquement aux spin-Orbits inoccupés.</span><span class="sxs-lookup"><span data-stu-id="c2476-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
