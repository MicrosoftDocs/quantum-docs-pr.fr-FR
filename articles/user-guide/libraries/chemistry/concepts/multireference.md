---
title: Fonctions d’onde corrélées
description: Découvrez les corrélations dynamiques et non dynamiques dans wavefunctions à l’aide de la bibliothèque Microsoft Quantum chimie.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: 420fc8e108852f6548e2147693e089f5ce970aa9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835483"
---
# <a name="correlated-wavefunctions"></a>Fonctions d’onde corrélées

Pour de nombreux systèmes, en particulier ceux proches de la géométrie d’équilibre, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) théorie fournit une description qualitative des propriétés moléculaires à l’aide d’un état de référence unique déterminant. Toutefois, pour obtenir une précision quantitative, vous devez également prendre en compte les effets de corrélation. 

Dans ce contexte, il est important de dinstinguish entre les corrélations dynamiques et non dynamiques.
Les corrélations dynamiques proviennent de la tendance des électrons à rester séparés, par exemple en raison d’une répulsion interélectronique. Cet effet peut être modelé en tenant compte des informations de l’état de référence des électrons. Des corrélations non dynamiques surviennent lorsque le wavefunction est dominé par deux configurations ou plus dans l’ordre avant toute chose, même pour obtenir uniquement une description qualitative du système.
Cela nécessite une superposition de déterminants et est un exemple de wavefunction à références multiréférence.

La bibliothèque chimie offre un moyen de spécifier un wavefunction de commande avant toute chose pour le problème de multiréférence comme superposition de déterminants. Cette approche, que nous appelons les wavefunctionss à plusieurs références éparses, est efficace lorsque seuls quelques composants suffisent à spécifier la superposition. La bibliothèque fournit également une méthode pour inclure des corrélations dynamiques sur une référence déterminante à l’aide de l’Ansatz d’unités généralisées de clusters couplés. En outre, il construit également des circuits quantiques qui génèrent ces États sur un ordinateur quantique. Ces États peuvent être spécifiés dans le [schéma Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), et nous fournissons également les fonctionnalités permettant de spécifier manuellement ces États via la bibliothèque chimie.

## <a name="sparse-multi-reference-wavefunction"></a>Wavefunction multi-Reference épars
Un État à plusieurs références $ \ket{\ psi_ {\rm {MCSCF}}} $ peut être spécifié explicitement comme une combinaison linéaire de $N le determininants $-Electron Slater.
\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots a ^ \ dagger_ {i_N} \ket {0} .
\end{align} par exemple, l’État $ \propto (0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ peut être spécifié dans la bibliothèque chimie comme suit.
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
Cette représentation explicite des composants de superposition est effective lorsque seuls quelques composants doivent être spécifiés. Il convient d’éviter d’utiliser cette représentation quand de nombreux composants sont requis pour capturer avec précision l’état souhaité. La raison est le coût de la porte du circuit Quantum qui prépare cet État sur un ordinateur quantique, qui met à l’échelle de façon linéaire avec le nombre de composants superposition, et au plus augmentera avec la norme unidimensionnelle des amplitudes de superposition.

## <a name="unitary-coupled-cluster-wavefunction"></a>Wavefunction de clusters couplés unitaires
Il est également possible de spécifier une wavefunction de clusters à \ket{\ d’unités $ psi_ {\rm {UCC}}} $ à l’aide de la bibliothèque chemistery. Dans ce cas, nous avons un état de référence unique déterminant, par exemple, $ \ket{\ psi_ {\rm{SCF}}} $. Les composants des wavefunction de clusters à couplage unitaire sont ensuite spécifiés implicitement via un opérateur unitaire agissant sur un état de référence.
Cet opérateur Unity est couramment écrit sous la forme $e ^ {T-T ^ \dagger} $, où $T-T ^ \dagger $ est l’opérateur de cluster anti-Hermitian. Par conséquent \begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.
\end{align}

Il est également courant de fractionner l’opérateur de cluster $T = T_1 + T_2 + \cdots $ en parties, où chaque partie $T _j $ contient $j termes $ Body. Dans la théorie généralisée de clusters couplés, l’opérateur de cluster à un corps (Single) se présente sous la forme \begin{align} T_1 = \ sum_ {PQ} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}

et l’opérateur de cluster à deux corps (double) se présente sous la forme \begin{align} T_2 = \ sum_ {PQRS} T ^ {PQ} _ {RS} a ^ \ dagger_p un ^ \ dagger_q a_r A_S.
\end{align}

Des conditions d’ordre supérieur (triples, quadruples, etc.) sont possibles, mais ne sont pas actuellement prises en charge par la bibliothèque chimie.

Par exemple, laissez $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} $ et laissez $T = 0,123 a ^ \ dagger_0 A_1 + 0,456 a ^ \ dagger_0a ^ \ dagger_3 A_1 a_2-0,789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $. Ensuite, cet État est instancié dans la bibliothèque chimie comme suit.
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

La sélection de spin convervation peut être rendue explicite en spécifiant `SpinOrbital` des index au lieu d’indices d’entiers. Par exemple, laissez $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} a ^ \ dagger_ {2, \downarrow}\ket {0} $ et laissez $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ is spin convserving. Ensuite, cet État est instancié dans la bibliothèque chimie comme suit.
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

Nous fournissons également une fonction pratique qui énumère tous les opérateurs de cluster de basculement qui Annihilate uniquement les spin-Orbits occupés et excitent uniquement aux spin-Orbits inoccupés.
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
