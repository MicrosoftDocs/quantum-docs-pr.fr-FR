---
title: Deuxième quantification
description: Découvrez la deuxième approche de quantification de la modélisation des structures électroniques dans la programmation quantique.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835806"
---
# <a name="second-quantization"></a><span data-ttu-id="f68f8-103">Deuxième quantification</span><span class="sxs-lookup"><span data-stu-id="f68f8-103">Second Quantization</span></span>

<span data-ttu-id="f68f8-104">La deuxième quantification examine le problème de la structure électronique par le biais d’une autre lentille.</span><span class="sxs-lookup"><span data-stu-id="f68f8-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="f68f8-105">Au lieu d’affecter chaque $N _e $ électron à un état spécifique (ou orbital), une deuxième quantification effectue le suivi de chaque orbital et stocke si un électron est présent dans chacun d’eux et, en même temps, garantit automatiquement les propriétés de symétrie de la fonction Wave correspondante.</span><span class="sxs-lookup"><span data-stu-id="f68f8-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="f68f8-106">Cela est important, car il permet de spécifier des modèles de chimie Quantum sans avoir à se soucier de l’état d’entrée symmetrizing (comme cela est requis pour fermions) et également parce que la deuxième quantification permet de simuler ces modèles à l’aide de petits ordinateurs Quantum.</span><span class="sxs-lookup"><span data-stu-id="f68f8-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="f68f8-107">En guise d’exemple de deuxième quantification en action, supposons que la valeur de $ \ psi_0 \cdots \ psi_ {N-1} $ est un ensemble orthonormal d’orbites spatiales.</span><span class="sxs-lookup"><span data-stu-id="f68f8-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="f68f8-108">Ces orbites sont choisies pour représenter le système aussi précisément que possible dans l’ensemble de base fini pris en compte.</span><span class="sxs-lookup"><span data-stu-id="f68f8-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="f68f8-109">Un exemple courant d’orbites est l’orbite atomique qui forme un eigenbasis pour l’Atom hydrogène.</span><span class="sxs-lookup"><span data-stu-id="f68f8-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="f68f8-110">Étant donné que les électrons ont deux États de rotation, deux électrons peuvent être sursubmergés dans chaque orbital spatial.</span><span class="sxs-lookup"><span data-stu-id="f68f8-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="f68f8-111">Autrement dit, les États de base valides se présentent sous la forme $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ où $ \uparrow $ et $ \downarrow $ sont des étiquettes qui spécifient les deux eigenstates du degré de liberté de spin.</span><span class="sxs-lookup"><span data-stu-id="f68f8-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="f68f8-112">Cet index combiné de $ (j, \sigma) $ pour $ \sigma \Dans \{ \uparrow, \downarrow \} $ est appelé spin-orbital, car il stocke le degré spatial et le degré de liberté de spin.</span><span class="sxs-lookup"><span data-stu-id="f68f8-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="f68f8-113">Dans la bibliothèque chimie, les orbites sont stockées dans une `SpinOrbital` structure de données et sont créées comme suit.</span><span class="sxs-lookup"><span data-stu-id="f68f8-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="f68f8-114">Cela signifie que nous pouvons imaginer officiellement la base pour la partie de rotation et spatiale de la fonction Wave en tant que $ \ psi_ {0} \cdots \ psi_ {2n-1} $ où chacun des index est maintenant une énumération d’un $ (j, \sigma) $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="f68f8-115">Une énumération possible est $g (j, \sigma) = j + N\sigma' $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="f68f8-116">Une autre énumération possible est $h (j, \sigma) = 2 \* j + \sigma $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="f68f8-117">La bibliothèque de chimie quantique peut utiliser ces conventions, et les orbites dans ce type d’encodage peuvent être instanciées comme suit.</span><span class="sxs-lookup"><span data-stu-id="f68f8-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="f68f8-118">Pour les systèmes fermionic, le principe d’exclusion Pauli empêche la présence de plusieurs électrons dans n’importe quel spin-orbital en même temps.</span><span class="sxs-lookup"><span data-stu-id="f68f8-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="f68f8-119">Cela signifie que nous pouvons écrire les deux États légaux pour $ \ psi_1 $ As \begin{Equation} \ psi_1 \rightarrow \begin{cases} \ket _ 1 {0} & \text{if $ \ psi_1 $ n’est pas occupé,} </span><span class="sxs-lookup"><span data-stu-id="f68f8-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="f68f8-120">\ket _ 1 {1} & _ \text{if $ \ psi_1 $ est occupé.}</span><span class="sxs-lookup"><span data-stu-id="f68f8-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="f68f8-121">\end{cases} \end{Equation} cet encodage est parfait pour les ordinateurs Quantum, car cela signifie que nous pouvons stocker l’occupation électronique comme un bit Quantum unique.</span><span class="sxs-lookup"><span data-stu-id="f68f8-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="f68f8-122">Les États de la profession pour les orbites de type « $ 2N $ » peuvent être stockés de la même façon dans $2N $ qubits.</span><span class="sxs-lookup"><span data-stu-id="f68f8-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="f68f8-123">Par exemple, si $N = $2, alors l’État $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="f68f8-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="f68f8-124">correspondrait aux orbites de rotation $1 $ et $2 $ en cours d’emploi avec le reste vide.</span><span class="sxs-lookup"><span data-stu-id="f68f8-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="f68f8-125">De même, l’État $ $ \ket {0} \equiv \ket {0} _ {0} \cdots \ket {0} _{N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="f68f8-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="f68f8-126">n’a aucun électron et est appelé « état de dépression ».</span><span class="sxs-lookup"><span data-stu-id="f68f8-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="f68f8-127">L’un des effets secondaires de la seconde quantification est que nous n’avons plus besoin de suivre explicitement l’anti-symétrie de l’État Quantum.</span><span class="sxs-lookup"><span data-stu-id="f68f8-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="f68f8-128">Cela est dû au fait que, comme nous le verrons, l’anti-symétrie de l’état représente lui-même à l’aide des règles anti-commutant des opérateurs qui créent et détruisent les occupations électroniques d’un spin orbital.</span><span class="sxs-lookup"><span data-stu-id="f68f8-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="f68f8-129">Fermionic, opérateurs</span><span class="sxs-lookup"><span data-stu-id="f68f8-129">Fermionic operators</span></span>

<span data-ttu-id="f68f8-130">Les deux opérateurs fondamentaux qui agissent sur les vecteurs de base de deuxième quantification sont appelés opérateurs de création et de annihilation.</span><span class="sxs-lookup"><span data-stu-id="f68f8-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="f68f8-131">Ces opérateurs insèrent ou détruisent des électrons à un emplacement particulier.</span><span class="sxs-lookup"><span data-stu-id="f68f8-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="f68f8-132">Celles-ci sont dénotées $a ^ \ dagger_j $ et $a _j $ respectivement.</span><span class="sxs-lookup"><span data-stu-id="f68f8-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="f68f8-133">Par exemple, \begin{align} a ^ \ dagger_1 \ket _ 1 {0} = \ket _ 1 {1} , \quad a ^ \ dagger_1 \ket _ 1 {1} = 0, \quad A_1 \ket _ 1 {0} = 0, \quad A_1 \ket {1} {0} _ 1 _ 1 _ 1.</span><span class="sxs-lookup"><span data-stu-id="f68f8-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="f68f8-134">\end{align} Notez que, ici $a ^ \ dagger_1 \ket _ 1 = 0 $ et $a _ 1 _ 1 _ 1 _ _ \ket _ 1 {1} {0} $ génère le vecteur zéro et non $ \ket _ 1 {0} $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="f68f8-135">Par conséquent, ces opérateurs ne sont ni Hermitian ni Unity.</span><span class="sxs-lookup"><span data-stu-id="f68f8-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="f68f8-136">Nous représentons les opérateurs de création générale et annihilation à l’aide du <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span><span class="sxs-lookup"><span data-stu-id="f68f8-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="f68f8-137">Par exemple, un opérateur de création unique est représenté comme suit.</span><span class="sxs-lookup"><span data-stu-id="f68f8-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="f68f8-138">En outre, à l’aide de ces opérateurs, nous pouvons exprimer $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}.</span><span class="sxs-lookup"><span data-stu-id="f68f8-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="f68f8-139">$ $ Cette séquence d’opérateurs serait construite au sein de la bibliothèque de simulation de Hamilton à l’aide d’un code C# similaire au cas orbital à simple vrille considéré ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="f68f8-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="f68f8-140">Pour un système de $k $ fermions, dans la seconde quantification, l’action de l’opérateur de création $a ^ \ dagger_i $ est donnée par $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ et $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $ où $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ mesure le nombre total de fermions qui sont dans l’état d’une seule particule et qui ont un index $j < i $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="f68f8-141">Un troisième opérateur est également souvent utilisé dans les deux représentations quantifiées.</span><span class="sxs-lookup"><span data-stu-id="f68f8-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="f68f8-142">Cet opérateur est appelé opérateur de nombre et est défini par \begin{Equation} n_i = a ^ \ dagger_i a_i.</span><span class="sxs-lookup"><span data-stu-id="f68f8-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="f68f8-143">\end{Equation} cet opérateur compte l’occupation d’un spin orbital donné, c’est-à-dire \begin{align} n_i \ket {0} _i &= 0 \ nonumber</span><span class="sxs-lookup"><span data-stu-id="f68f8-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="f68f8-144">n_i \ket {1} _i &= \ket {1} _i.</span><span class="sxs-lookup"><span data-stu-id="f68f8-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="f68f8-145">\end{align} similaire aux exemples ci-dessus `FermionTerm` , cet opérateur de nombre est construit comme suit.</span><span class="sxs-lookup"><span data-stu-id="f68f8-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="f68f8-146">Une subtilité émerge cependant lors de l’utilisation d’opérateurs de création ou de annihilation dans les systèmes fermionic.</span><span class="sxs-lookup"><span data-stu-id="f68f8-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="f68f8-147">Nous exigeons que tout état Quantum valide soit anti-symétrique dans le cadre de l’échange d’étiquettes.</span><span class="sxs-lookup"><span data-stu-id="f68f8-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="f68f8-148">Cela signifie que $ $ a ^ \ dagger_2 un ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 un ^ \ dagger_2 \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="f68f8-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="f68f8-149">Les opérateurs $ $ sont dits « anti-muet » et, en général, pour tout $i, j $ nous avons \begin{align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.</span><span class="sxs-lookup"><span data-stu-id="f68f8-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="f68f8-150">\end{align} donc les deux <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances suivantes sont considérées comme inéquivalentes</span><span class="sxs-lookup"><span data-stu-id="f68f8-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="f68f8-151">L’exigence que chacun des opérateurs de création anti-piratage signifie que l’utilisation d’une seconde représentation quantifiée permet d’éviter les défis liés à l’anti-symétrie de fermions.</span><span class="sxs-lookup"><span data-stu-id="f68f8-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="f68f8-152">Au lieu de cela, le défi émerge à nouveau dans la définition des opérateurs de création.</span><span class="sxs-lookup"><span data-stu-id="f68f8-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="f68f8-153">À l’aide des règles anti-commutation, certaines `LadderSequence` instances correspondent en fait à la même séquence d’opérateurs fermionic, parfois jusqu’à un signe moins.</span><span class="sxs-lookup"><span data-stu-id="f68f8-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="f68f8-154">Par exemple, considérez la $a de la _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="f68f8-155">Cela nous incite à définir un classement canonique pour chaque `FermionTerm` .</span><span class="sxs-lookup"><span data-stu-id="f68f8-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="f68f8-156">Tout `FermionTerm` est automatiquement placé dans l’ordre canonique comme suit.</span><span class="sxs-lookup"><span data-stu-id="f68f8-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="f68f8-157">Deuxième Fermionic Hamilton</span><span class="sxs-lookup"><span data-stu-id="f68f8-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="f68f8-158">Il est peut-être trop surprenant que les [modèles quantiques pour les systèmes électroniques](xref:microsoft.quantum.chemistry.concepts.quantummodels) puissent être écrits en termes de création et d’opérateurs de annihilation.</span><span class="sxs-lookup"><span data-stu-id="f68f8-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="f68f8-159">En particulier, si $ \Psi \_ j $ est les orbites de spin qui forment la base,</span><span class="sxs-lookup"><span data-stu-id="f68f8-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="f68f8-160">\begin{Equation} \hat{H} = \sum \_ {PQ} h \_ {PQ} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {PQRS} h \_ {PQRS} a ^ \dagger \_ p a ^ \dagger \_ q a \_ RA \_ s + h \_ {\textrm NUC}, \label{EQ : totalHam} \end{Equation}, où $h \_ {\textrm NUC} $ est l’énergie nucléaire (qui est une constante sous la approximation Oppenheimer) et</span><span class="sxs-lookup"><span data-stu-id="f68f8-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="f68f8-161">\begin{align} h \_ {PQ} &= \int \_ {-\infty} ^ \infty \Psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \Psi \_ q (x \_ 1) \mathrm{d} ^ 3x \_ 1, \end{align}</span><span class="sxs-lookup"><span data-stu-id="f68f8-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="f68f8-162">où $V (x) $ est le potentiel du champ de moyenne, et</span><span class="sxs-lookup"><span data-stu-id="f68f8-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="f68f8-163">\begin{align} h \_ {PQRS} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \Psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| X_1-X_2 |} \right) \Psi \_ r (x \_ 2) \Psi \_ s (x \_ 1) \mathrm{d} ^ 3x \_ 1 \ mathrm {d} ^ 3x \_ 2. \ label {EQ : intégrales} \end{align}</span><span class="sxs-lookup"><span data-stu-id="f68f8-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="f68f8-164">Les termes $h \_ {PQ} $ sont appelés intégrales à un seul électron, car tous ces termes n’impliquent que des électrons uniques et, de même $h \_ {PQRS} $ sont des intégrales à deux électrons.</span><span class="sxs-lookup"><span data-stu-id="f68f8-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="f68f8-165">Ils sont appelés des intégraux, car le calcul des valeurs de ces coefficients requiert un intégral.</span><span class="sxs-lookup"><span data-stu-id="f68f8-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="f68f8-166">Les termes d’un électron décrivent l’énergie cinétique des électrons individuels et leurs interactions avec les champs électriques du noyau.</span><span class="sxs-lookup"><span data-stu-id="f68f8-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="f68f8-167">Les deux intégrales d’électrons, quant à eux, décrivent les interactions entre les électrons.</span><span class="sxs-lookup"><span data-stu-id="f68f8-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="f68f8-168">Une intuition pour ce que ces termes signifie peuvent être collectées à partir des opérateurs de création et de annihilation qui composent chacun d’eux.</span><span class="sxs-lookup"><span data-stu-id="f68f8-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="f68f8-169">Par exemple, $h _ {PQ} a ^ \ dagger_p a_q $ décrit les sauts d’électrons de spin orbital $q $ à spin orbital $p $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="f68f8-170">De même, le terme $h _ {PQRS} a ^ \ dagger_p un ^ \ dagger_q a_r a_s $ (pour distinct $p, q, r, s $) décrit deux électrons dans des orbites de spins $r $ et $s $ Dispersing et se terminant par des orbites de rotation $p $ et $q $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="f68f8-171">Si $r = q $ et $p = s $ Then $h _ {PRRP} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {PRRP} n_p n_r $ donne la pénalité d’énergie associée aux deux électrons proches les uns des autres, mais ne décrit pas un processus dynamique.</span><span class="sxs-lookup"><span data-stu-id="f68f8-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="f68f8-172">Nous pouvons représenter ces Hamiltonians à l’aide de la `FermionHamiltonian` classe, qui est essentiellement une liste contenant toutes les instances souhaitées `FermionTerm` .</span><span class="sxs-lookup"><span data-stu-id="f68f8-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="f68f8-173">Comme les Hamiltonians sont Hermitian par définition, nous indexons les termes à l’aide du type plus spécialisé `HermitianFermionTerm` qui utilise également la symétrie Hermitian pour vérifier si les termes sont équivalents.</span><span class="sxs-lookup"><span data-stu-id="f68f8-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="f68f8-174">Créons quelques exemples illustrant cet exemple.</span><span class="sxs-lookup"><span data-stu-id="f68f8-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="f68f8-175">Considérez le \hat{H} de Hamilton $ = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="f68f8-176">Nous pouvons simplifier cette construction en utilisant les opérateurs de Hermitian.</span><span class="sxs-lookup"><span data-stu-id="f68f8-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="f68f8-177">Lors de l’ajout de termes à la Hamilton à l’aide de `Add` , tout terme non Hermitian tel que `fermionTerm0` est supposé être associé à son conjugué Hermitian.</span><span class="sxs-lookup"><span data-stu-id="f68f8-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="f68f8-178">Ainsi, l’extrait de code suivant représente également le même Hamilton :</span><span class="sxs-lookup"><span data-stu-id="f68f8-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="f68f8-179">À l’aide des règles de protection contre la permutation, certaines `FermionTerm` instances dans le cas de la Hamilton correspondent en fait à la même séquence d’opérateurs fermionic, parfois jusqu’à un signe moins.</span><span class="sxs-lookup"><span data-stu-id="f68f8-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="f68f8-180">Par exemple, considérez le $H Hamiltony = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, qui est une somme des termes construits ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="f68f8-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="f68f8-181">Il n’est pas toujours évident pour l’utilisateur qu’il s’agit de termes équivalents, et par conséquent, ils peuvent être ajoutés séparément à la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="f68f8-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="f68f8-182">Vous pouvez également être intéressé par la modification de termes déjà existants dans le même lieu.</span><span class="sxs-lookup"><span data-stu-id="f68f8-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="f68f8-183">Dans ces cas-là, nous pouvons combiner les termes équivalents comme suit.</span><span class="sxs-lookup"><span data-stu-id="f68f8-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="f68f8-184">En associant des coefficients de termes équivalents, nous réduisons le nombre total de termes dans le même niveau de Hamilton.</span><span class="sxs-lookup"><span data-stu-id="f68f8-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="f68f8-185">Plus tard, cela réduit le nombre de portes de Quantum nécessaires pour simuler le niveau de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="f68f8-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="f68f8-186">Représentation interne</span><span class="sxs-lookup"><span data-stu-id="f68f8-186">Internal Representation</span></span>

<span data-ttu-id="f68f8-187">Un fermionic Hamilton avec des interactions d’un et de deux corps est représenté par une seconde notation quantifiée comme</span><span class="sxs-lookup"><span data-stu-id="f68f8-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="f68f8-188">$ $ \begin{align} H = \sum \_ {PQ} H \_ {PQ} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {PQRS} H \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s}.</span><span class="sxs-lookup"><span data-stu-id="f68f8-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="f68f8-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f68f8-189">\end{align} $$</span></span>

<span data-ttu-id="f68f8-190">Dans cette notation, il existe au maximum $N ^ 2 + N ^ 4 $ coefficients.</span><span class="sxs-lookup"><span data-stu-id="f68f8-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="f68f8-191">Toutefois, un grand nombre de ces coefficients peuvent être collectés, car ils correspondent au même opérateur.</span><span class="sxs-lookup"><span data-stu-id="f68f8-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="f68f8-192">Par exemple, dans le cas où $p, q, r, s $ sont des index distincts, nous pouvons utiliser les règles anti-commutation pour indiquer que : $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {r} a {s} \_ =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a {s} = a \_ \_ ^ \dagger \_ {q} a ^ \dagger \_ {p} \_ \_ a {r}.</span><span class="sxs-lookup"><span data-stu-id="f68f8-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="f68f8-193">En outre, comme $H $ est Hermitian, chaque opérateur fermionic non-Hermitian, par exemple $h \_ {PQRS} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $, a un conjugué Hermitian qui est également trouvé dans $H $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="f68f8-194">Afin d’indexer de manière unique des groupes de termes caractérisés par ces Symmetries, nous définissons un classement canonique sur les index $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) de toute séquence d’opérateurs $n + m $ fermionic $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $As suit :</span><span class="sxs-lookup"><span data-stu-id="f68f8-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="f68f8-195">Tous les opérateurs de création $a ^ \dagger \_ {i \_ \cdot} $ sont placés avant tous les opérateurs annihilation $a \_ {j \_ \cdot} $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="f68f8-196">Tous les index d’opérateur de création sont triés par ordre croissant, c’est-à-dire $i \_ 1< i \_ 2< \cdots < i \_ n $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="f68f8-197">Tous les index d’opérateur annihilation sont triés par ordre décroissant, c’est-à-dire $j \_ 1> j \_ 2 \cdots > j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="f68f8-198">L’index le plus à gauche est inférieur ou égal à l’index le plus à droite, autrement dit $i \_ 1 \ le j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="f68f8-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="f68f8-199">Nous allons identifier cet ensemble d’index ordonnés de manière canonique comme $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \Dans S \_ {n, m}.</span><span class="sxs-lookup"><span data-stu-id="f68f8-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="f68f8-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f68f8-200">\end{align} $$</span></span>

<span data-ttu-id="f68f8-201">Avec ce classement canonique, le fermionic Hamilton peut être exprimé sous la forme $ $ \begin{align} H = \sum \_ {(p, q) \Dans S \_ {1,1} } H' \_ {PQ} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \Dans s \_ {2,2} } H « \_ {PQRS} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $ avec des intégraux unidirectionnels à un et à deux électrons $h' \_ {PQ} $ et $h' \_ {PQRS} $, respectivement.</span><span class="sxs-lookup"><span data-stu-id="f68f8-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

