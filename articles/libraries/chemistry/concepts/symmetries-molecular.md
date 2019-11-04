---
title: Symmetries de l’intégrale moléculaire | Microsoft Docs
description: Symmetries des documents conceptuels de intégrale moléculaire
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442399"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries de l’intégrale moléculaire

La symétrie inhérente de la Coulomb Hamilton, qui est le lieu de la Hamilton dans les [modèles quantiques pour les systèmes électroniques](xref:microsoft.quantum.chemistry.concepts.quantummodels), qui décrit les électrons qui interagissent de façon électrique entre eux et avec le noyau, conduit à un certain nombre de Symmetries pouvant être vous avez été exploité pour compresser les termes dans le cadre de la Hamilton.
En général, si aucune autre hypothèse n’est prise sur les fonctions de base $ \psi_j $, nous avons uniquement ce \begin{Equation} H_ {PQRS} = H_ {qpsr}, \tag{★} \label{EQ : hpqrs} \end{Equation} qui peut être immédiatement vu des intégraux dans les [modèles Quantum pour Les systèmes électroniques](xref:microsoft.quantum.chemistry.concepts.quantummodels) à noter que leurs valeurs restent identiques si $p, q $ et $r, s $ sont interchangeables par rapport à l’anti-mutation.

Si nous supposons que les orbites sont réellement évaluées (comme c’est le cas pour les bases orbitales Gaussienles), nous avons ensuite les \begin{Equation} H_ {PQRS} = H_ {qpsr} = H_ {srqp} = H_ {rspq} = H_ {rqps} = H_ {psrq} = H_ {SPQR} = H_ {qrsp} .\tag {★} \label{EQ : hpqrsreal} Equation} étant donné la conservation de ces hypothèses, nous pouvons utiliser les Symmetries ci-dessus pour réduire les données nécessaires au stockage des éléments de matrice du type Hamilton en utilisant un facteur de $8 $; Bien que cela rende l’importation des données d’une manière cohérente un peu plus complexe.
Heureusement, la bibliothèque de simulation de la Hamilton contient des sous-routines qui peuvent être utilisées pour importer des fichiers intégraux à partir de [Liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) ou directement à partir de [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).

Les intégraux ORBITALS moléculaires (c’est-à-dire les $h\_{PQ} $ et $h\_{PQRS} $) tels que ceux-ci sont représentés à l’aide du type `OrbitalIntegral`, qui fournit un certain nombre de fonctions utiles pour exprimer cette symétrie.
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

En plus de l’énumération de tous les intégrales orbitales qui sont numériquement identiques, une liste de tous les indices spin-orbital contenus dans le sous-sein de la même manière, représentée par un `OrbitalIntegral` peut être générée comme suit.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Construction de Hamiltonians Fermionic à partir de intégrales moléculaires

Au lieu de construire un Fermionic Hamilton en ajoutant `FermionTerm`s, tous les termes correspondant à chaque intégrale orbital peuvent être ajoutés automatiquement.
Par exemple, le code suivant énumère automatiquement toutes les Symmetries permutations et trie les termes dans l’ordre canonique : 
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
