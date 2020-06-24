---
title: Hartree-Fock théorie
description: Découvrez la théorie Hartree – Fock, un moyen simple de construire l’état initial des systèmes quantiques.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275108"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="491c9-103">Hartree – théorie Fock</span><span class="sxs-lookup"><span data-stu-id="491c9-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="491c9-104">La quantité la plus importante de la simulation de chimie quantique est peut-être l’état du sol, qui est le extraction d’énergie minimal de la matrice de la région de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="491c9-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="491c9-105">Cela est dû au fait que, pour la plupart des molécules, les quantités de température ambiante, telles que les taux de réaction, sont dominées par les différences d’énergie gratuites entre les États quantiques qui décrivent le début et la fin d’une étape dans une voie de réaction et à la température ambiante, cet état intermédiaire est généralement des États de sol.</span><span class="sxs-lookup"><span data-stu-id="491c9-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="491c9-106">Bien que l’état du sol soit généralement trop difficile à apprendre (même avec un ordinateur quantique), car il s’agit d’une distribution sur un nombre de configurations exponentiellement élevé.</span><span class="sxs-lookup"><span data-stu-id="491c9-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="491c9-107">Des quantités telles que l’énergie de l’état du sol peuvent être apprises.</span><span class="sxs-lookup"><span data-stu-id="491c9-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="491c9-108">Par exemple, si $ \ket{\Psi} $ est un État Quantum pur, \begin{Equation} E = \bra{\Psi} \hat{H} \ket{\Psi} \end{Equation} donne l’énergie moyenne que le système a dans cet État.</span><span class="sxs-lookup"><span data-stu-id="491c9-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="491c9-109">L’état du sol est alors l’État qui donne le plus petit de cette valeur.</span><span class="sxs-lookup"><span data-stu-id="491c9-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="491c9-110">Par conséquent, le choix d’un état aussi proche que possible du véritable État du sol est vital pour l’estimation de l’énergie directement (comme c’est le cas dans les eigensolverss de variation) ou par l’estimation de phase.</span><span class="sxs-lookup"><span data-stu-id="491c9-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="491c9-111">Hartree – Fock théorie offre un moyen simple de construire l’état initial des systèmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="491c9-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="491c9-112">Il produit une approximation Slater déterminante à l’état du sol d’un système Quantum.</span><span class="sxs-lookup"><span data-stu-id="491c9-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="491c9-113">À cette fin, il trouve une rotation dans Fock-Space qui minimise l’énergie de l’état du sol.</span><span class="sxs-lookup"><span data-stu-id="491c9-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="491c9-114">En particulier, pour un système de $N $ Electron, la méthode effectue la rotation \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} avec un anti-Hermitian (c.-à-d. $u =-u ^ \dagger $) matrice $u = \ sum_ {PQ} U_ {PQ} a ^ \ dagger_p a_q $.</span><span class="sxs-lookup"><span data-stu-id="491c9-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="491c9-115">Il convient de noter que la matrice $u $ représente les rotations orbitales et $ \widetilde{a} ^ \ dagger_j $ et $ \widetilde{a} _j $ représentent les opérateurs de création et de annihilation pour les électrons occupant Hartree – Fock des orbites moléculaires moléculaires.</span><span class="sxs-lookup"><span data-stu-id="491c9-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="491c9-116">La matrice $u $ est ensuite optimisée pour réduire l’énergie attendue $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="491c9-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="491c9-117">Ces problèmes d’optimisation peuvent être génériques, en pratique, l’algorithme Hartree – Fock tend à converger rapidement vers une solution presque optimale pour le problème d’optimisation, en particulier pour les molécules de Shell fermé dans les géométries d’équilibre.</span><span class="sxs-lookup"><span data-stu-id="491c9-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="491c9-118">Nous pouvons spécifier ces États en tant qu’instance de l' `FermionWavefunction` objet.</span><span class="sxs-lookup"><span data-stu-id="491c9-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="491c9-119">Par exemple, l’État $a ^ \ dagger_ {1} un ^ \ dagger_ {2} un ^ \ dagger_ {6} \ket {0} $ est instancié dans la bibliothèque chimie comme suit.</span><span class="sxs-lookup"><span data-stu-id="491c9-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="491c9-120">Il est également possible d’indexer des fonctions Wave avec des index `SpinOrbital` , puis de convertir ces index en entiers, comme suit.</span><span class="sxs-lookup"><span data-stu-id="491c9-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="491c9-121">La fonctionnalité la plus saisissante de la théorie Hartree – Fock est qu’elle produit un État Quantum qui n’a aucun enchevêtrement entre les électrons.</span><span class="sxs-lookup"><span data-stu-id="491c9-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="491c9-122">Cela signifie qu’elle fournit souvent une description qualitative appropriée des propriétés des systèmes moléculaires.</span><span class="sxs-lookup"><span data-stu-id="491c9-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="491c9-123">L’État Hartree-Fock peut également être reconstruit à partir d’un `FermionHamiltonian` comme suit.</span><span class="sxs-lookup"><span data-stu-id="491c9-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="491c9-124">Toutefois, l’obtention de résultats exacts, en particulier pour les systèmes fortement corrélés, nécessite des États quantiques qui vont au-delà de la théorie Hartree – Fock.</span><span class="sxs-lookup"><span data-stu-id="491c9-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
