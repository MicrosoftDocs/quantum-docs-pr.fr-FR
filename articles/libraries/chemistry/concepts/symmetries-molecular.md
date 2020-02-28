---
title: Symmetries de l’intégrale moléculaire
description: 'En savoir plus sur l’utilisation du type Q # OrbitalIntegral pour énumérer les Symmetries moléculaires.'
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: b7e7b79af17af544c4a784eff08500498afc9f67
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904466"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="affac-103">Symmetries de l’intégrale moléculaire</span><span class="sxs-lookup"><span data-stu-id="affac-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="affac-104">La symétrie inhérente de la Coulomb Hamilton, qui est le lieu de la Hamilton dans les [modèles quantiques pour les systèmes électroniques](xref:microsoft.quantum.chemistry.concepts.quantummodels), qui décrit l’interaction entre les électrons et les noyaux, conduit à un certain nombre de Symmetries qui peuvent être exploités pour compresser les termes dans le système de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="affac-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="affac-105">En général, si aucune autre hypothèse n’est prise sur les fonctions de base $ \ psi_j $, nous n’avons que cette \begin{Equation} h_ {PQRS} = h_ {qpsr}, \tag{★} \label{EQ : hpqrs} \end{Equation} qui peut être immédiatement vu des intégraux dans les [modèles Quantum pour les systèmes électroniques](xref:microsoft.quantum.chemistry.concepts.quantummodels) , à noter que leurs valeurs restent identiques si $p, q $ et $r, s $ sont interchangeables par rapport à l’anti-commutation.</span><span class="sxs-lookup"><span data-stu-id="affac-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="affac-106">Si nous partons du principe que les orbites sont réellement évaluées (comme c’est le cas pour les bases orbitales Gaussienles), nous avons ensuite cette \begin{Equation} h_ {PQRS} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} psrq {H_} SPQR : qrsp} .\tag Equation} étant donné la conservation de ces hypothèses, nous pouvons utiliser les Symmetries ci-dessus pour réduire les données nécessaires au stockage des éléments de matrice du type Hamilton en utilisant un facteur de $8 $; Bien que cela rende l’importation des données d’une manière cohérente un peu plus complexe.</span><span class="sxs-lookup"><span data-stu-id="affac-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="affac-107">Heureusement, la bibliothèque de simulation de la Hamilton contient des sous-routines qui peuvent être utilisées pour importer des fichiers intégraux à partir de [Liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) ou directement à partir de [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span><span class="sxs-lookup"><span data-stu-id="affac-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="affac-108">Les intégraux ORBITALS moléculaires (c’est-à-dire les $h\_{PQ} $ et $h\_{PQRS} $) tels que ceux-ci sont représentés à l’aide du type `OrbitalIntegral`, qui fournit un certain nombre de fonctions utiles pour exprimer cette symétrie.</span><span class="sxs-lookup"><span data-stu-id="affac-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

<span data-ttu-id="affac-109">En plus de l’énumération de tous les intégrales orbitales qui sont numériquement identiques, une liste de tous les indices spin-orbital contenus dans le sous-sein de la même manière, représentée par un `OrbitalIntegral` peut être générée comme suit.</span><span class="sxs-lookup"><span data-stu-id="affac-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="affac-110">Construction de Hamiltonians Fermionic à partir de intégrales moléculaires</span><span class="sxs-lookup"><span data-stu-id="affac-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="affac-111">Au lieu de construire un Fermionic Hamilton en ajoutant `FermionTerm`s, tous les termes correspondant à chaque intégrale orbital peuvent être ajoutés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="affac-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="affac-112">Par exemple, le code suivant énumère automatiquement toutes les Symmetries permutations et trie les termes dans l’ordre canonique :</span><span class="sxs-lookup"><span data-stu-id="affac-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
