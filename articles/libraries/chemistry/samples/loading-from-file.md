---
title: Chargement d’un Hamiltonien à partir d’un fichier
description: Découvrez comment générer automatiquement un grand degré de Hamilton à l’aide du schéma Broombridge.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 715dbcefc10ecc5af45f2bdd228890f1cb28886b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907288"
---
# <a name="loading-a-hamiltonian-from-file"></a>Chargement d’un Hamiltonien à partir d’un fichier
Auparavant, nous avons construit Hamiltonians en y ajoutant des termes. Bien que cela soit parfait pour les petits exemples, la chimie quantique à l’échelle nécessite Hamiltonians avec des millions ou des milliards de termes. Ces Hamiltonians, générés par des packages de chimie tels que NWChem, sont trop volumineux pour être importés manuellement. Dans cet exemple, nous illustrons comment une instance de `FermionHamiltonian` peut être générée automatiquement à partir d’une molécule représentée par le [schéma Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge). Pour référence, vous pouvez inspecter l’exemple de `LithiumHydrideGUI` fourni ou l’exemple `RunSimulation`. Une prise en charge limitée est également disponible pour l’importation à partir du format consommé par [LIQUi | >](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).

Prenons l’exemple de la molécule d’azote, fourni dans le dossier `IntegralData/YAML` du référentiel d’exemples. La méthode de chargement du schéma `Broombridge` est simple.

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Le schéma Broombridge contient également des suggestions pour l’état initial à préparer. Les étiquettes, par exemple `"|G⟩"` ou `"|E1⟩"`, pour ces États peuvent être consultées en inspectant le fichier. Afin de préparer ces États initiaux, les `qSharpData` consommées par les algorithmes Quantum Q # sont obtenues de la même façon que la [section précédente](xref:microsoft.quantum.chemistry.examples.energyestimate), mais avec un paramètre supplémentaire qui sélectionne l’état initial souhaité. Par exemple,
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Toutes les étapes ci-dessus peuvent être abrégées à l’aide des méthodes de commodité fournies comme suit.
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

Nous pouvons également charger un modèle Hamilton à partir du format LIQUi | >, à l’aide d’une syntaxe très similaire. 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

En suivant ce processus à partir de n’importe quelle instance de Broombridge, ou de n’importe quelle étape intermédiaire, les algorithmes Quantum tels que l’estimation de phase quantique peuvent être exécutés sur le problème de structure électronique spécifié.
