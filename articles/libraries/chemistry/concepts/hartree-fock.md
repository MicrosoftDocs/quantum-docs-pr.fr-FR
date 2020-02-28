---
title: Hartree-Fock théorie
description: Découvrez la théorie Hartree – Fock, un moyen simple de construire l’état initial des systèmes quantiques.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904449"
---
# <a name="hartreefock-theory"></a>Hartree – théorie Fock

La quantité la plus importante de la simulation de chimie quantique est peut-être l’état du sol, qui est le extraction d’énergie minimal de la matrice de la région de la Hamilton.
Cela est dû au fait que, pour la plupart des molécules, les quantités de température ambiante, telles que les taux de réaction, sont dominées par les différences d’énergie gratuites entre les États quantiques qui décrivent le début et la fin d’une étape dans une voie de réaction et à la température ambiante comme intermédiaire l’État est généralement des États de masse.
Bien que l’état du sol soit généralement trop difficile à apprendre (même avec un ordinateur quantique), car il s’agit d’une distribution sur un nombre de configurations exponentiellement élevé.
Des quantités telles que l’énergie de l’état du sol peuvent être apprises.
Par exemple, si $ \ket{\Psi} $ est un État Quantum pur, \begin{Equation} E = \bra{\Psi} \hat{H} \ket{\Psi} \end{Equation} donne l’énergie moyenne que le système a dans cet État.
L’état du sol est alors l’État qui donne le plus petit de cette valeur. Par conséquent, le choix d’un état aussi proche que possible du véritable État du sol est vital pour l’estimation de l’énergie directement (comme c’est le cas dans les eigensolverss de variation) ou par l’estimation de phase.

Hartree – Fock théorie offre un moyen simple de construire l’état initial des systèmes quantiques. Il produit une approximation Slater déterminante à l’état du sol d’un système Quantum. À cette fin, il trouve une rotation dans Fock-Space qui minimise l’énergie de l’état du sol. En particulier, pour un système de $N $ Electron, la méthode effectue la rotation \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket{0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket{0}\defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket{0}, \end{Equation} avec un anti-Hermitian (c.-à-d. $u =-u ^ \dagger $) matrice $u = \ sum_ {PQ} u_ {PQ} a ^ \ dagger_p a_q $. Il convient de noter que la matrice $u $ représente les rotations orbitales et $ \widetilde{a} ^ \ dagger_j $ et $ \widetilde{a} _j $ représentent les opérateurs de création et de annihilation pour les électrons occupant Hartree – Fock des orbites moléculaires moléculaires.


La matrice $u $ est ensuite optimisée pour réduire l’énergie attendue $ \bra{0} \ prod_ {j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket{0}$. Ces problèmes d’optimisation peuvent être génériques, en pratique, l’algorithme Hartree – Fock tend à converger rapidement vers une solution presque optimale pour le problème d’optimisation, en particulier pour les molécules de Shell fermé dans les géométries d’équilibre. Nous pouvons spécifier ces États en tant qu’instance de l’objet `FermionWavefunction`. Par exemple, l’État $a ^ \ dagger_{1}un ^ \ dagger_{2}un ^ \ dagger_{6}\ket{0}$ est instancié dans la bibliothèque chimie comme suit.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Il est également possible d’indexer des fonctions Wave avec des index `SpinOrbital`, puis de convertir ces index en entiers comme suit.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

La fonctionnalité la plus saisissante de la théorie Hartree – Fock est qu’elle produit un État Quantum qui n’a aucun enchevêtrement entre les électrons.
Cela signifie qu’elle fournit souvent une description qualitative appropriée des propriétés des systèmes moléculaires. 

L’État Hartree-Fock peut également être reconstruit à partir d’un `FermionHamiltonian` comme suit.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Toutefois, l’obtention de résultats exacts, en particulier pour les systèmes fortement corrélés, nécessite des États quantiques qui vont au-delà de la théorie Hartree – Fock.
