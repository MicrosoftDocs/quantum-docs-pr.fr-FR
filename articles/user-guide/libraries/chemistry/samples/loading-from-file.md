---
title: Chargement d’un Hamiltonien à partir d’un fichier
description: Découvrez comment générer automatiquement un grand degré de Hamilton à l’aide du schéma Broombridge.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 715dbcefc10ecc5af45f2bdd228890f1cb28886b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274728"
---
# <a name="loading-a-hamiltonian-from-file"></a><span data-ttu-id="c3bea-103">Chargement d’un Hamiltonien à partir d’un fichier</span><span class="sxs-lookup"><span data-stu-id="c3bea-103">Loading a Hamiltonian from file</span></span>
<span data-ttu-id="c3bea-104">Auparavant, nous avons construit Hamiltonians en y ajoutant des termes.</span><span class="sxs-lookup"><span data-stu-id="c3bea-104">Previously, we constructed Hamiltonians by adding individual terms to it.</span></span> <span data-ttu-id="c3bea-105">Bien que cela soit parfait pour les petits exemples, la chimie quantique à l’échelle nécessite Hamiltonians avec des millions ou des milliards de termes.</span><span class="sxs-lookup"><span data-stu-id="c3bea-105">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="c3bea-106">Ces Hamiltonians, générés par des packages de chimie tels que NWChem, sont trop volumineux pour être importés manuellement.</span><span class="sxs-lookup"><span data-stu-id="c3bea-106">Such Hamiltonians, generated by chemistry packages such as NWChem, are too large to import by hand.</span></span> <span data-ttu-id="c3bea-107">Dans cet exemple, nous illustrons comment une `FermionHamiltonian` instance peut être générée automatiquement à partir d’une molécule représentée par le [schéma Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="c3bea-107">In this sample, we illustrate how a `FermionHamiltonian` instance may be automatically generated from a molecule represented by the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span> <span data-ttu-id="c3bea-108">Pour référence, vous pouvez inspecter l' `LithiumHydrideGUI` exemple fourni ou l' `RunSimulation` exemple.</span><span class="sxs-lookup"><span data-stu-id="c3bea-108">For reference, one may inspect the provided `LithiumHydrideGUI` sample, or the `RunSimulation` sample.</span></span> <span data-ttu-id="c3bea-109">Une prise en charge limitée est également disponible pour l’importation à partir du format consommé par [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).</span><span class="sxs-lookup"><span data-stu-id="c3bea-109">Limited support is also available for importing from the format consumed by [LIQUi|>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).</span></span>

<span data-ttu-id="c3bea-110">Prenons l’exemple de la molécule d’azote, fourni dans le `IntegralData/YAML` dossier du référentiel d’exemples.</span><span class="sxs-lookup"><span data-stu-id="c3bea-110">Let us consider the example of the Nitrogen molecule, which is provided in the `IntegralData/YAML` folder of the samples repository.</span></span> <span data-ttu-id="c3bea-111">La méthode de chargement du `Broombridge` schéma est simple.</span><span class="sxs-lookup"><span data-stu-id="c3bea-111">The method for loading the `Broombridge` schema is straightforward.</span></span>

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

<span data-ttu-id="c3bea-112">Le schéma Broombridge contient également des suggestions pour l’état initial à préparer.</span><span class="sxs-lookup"><span data-stu-id="c3bea-112">The Broombridge schema also contains suggestions for the initial state to be prepared.</span></span> <span data-ttu-id="c3bea-113">Les étiquettes, par exemple `"|G⟩"` ou `"|E1⟩"` , pour ces États, peuvent être consultées en inspectant le fichier.</span><span class="sxs-lookup"><span data-stu-id="c3bea-113">The labels, e.g. `"|G⟩"` or `"|E1⟩"`, for these states may be seen by inspecting the file.</span></span> <span data-ttu-id="c3bea-114">Pour préparer ces États initiaux, le `qSharpData` consommé par les algorithmes Quantum Q # est obtenu de la même façon que la [section précédente](xref:microsoft.quantum.chemistry.examples.energyestimate), mais avec un paramètre supplémentaire qui sélectionne l’état initial souhaité.</span><span class="sxs-lookup"><span data-stu-id="c3bea-114">In order to prepare these initial states, the `qSharpData` consumed by the Q# quantum algorithms is obtained similar to the [previous section](xref:microsoft.quantum.chemistry.examples.energyestimate), but with an additional parameter selecting the desired initial state.</span></span> <span data-ttu-id="c3bea-115">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="c3bea-115">For instance,</span></span>
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

<span data-ttu-id="c3bea-116">Toutes les étapes ci-dessus peuvent être abrégées à l’aide des méthodes de commodité fournies comme suit.</span><span class="sxs-lookup"><span data-stu-id="c3bea-116">All the above steps may be abbreviated using provided convenience methods as follows.</span></span>
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

<span data-ttu-id="c3bea-117">Nous pouvons également charger un LIQUi Hamilton à partir du |> format, à l’aide d’une syntaxe très similaire.</span><span class="sxs-lookup"><span data-stu-id="c3bea-117">We may also load a Hamiltonian from the LIQUi|> format, using a very similar syntax.</span></span> 

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

<span data-ttu-id="c3bea-118">En suivant ce processus à partir de n’importe quelle instance de Broombridge, ou de n’importe quelle étape intermédiaire, les algorithmes Quantum tels que l’estimation de phase quantique peuvent être exécutés sur le problème de structure électronique spécifié.</span><span class="sxs-lookup"><span data-stu-id="c3bea-118">By following this process from any instance of Broombridge, or any intermediate step, quantum algorithms such as quantum phase estimation may be run on the specified electronic structure problem.</span></span>