---
title: Exemple de programme Quantum NWChem
description: À l’aide d’un pont d’entrée NWChem, passez en revue un exemple d’obtention du nombre de portes pour la simulation de chimie quantique.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 7605676e05ee352e47791657eeaafceef5dbb493
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274736"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="d6c84-103">De bout en bout avec NWChem</span><span class="sxs-lookup"><span data-stu-id="d6c84-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="d6c84-104">Dans cet article, vous allez découvrir un exemple d’obtention du nombre de portes pour la simulation de la chimie quantique, à partir d’un pont d’entrée [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .</span><span class="sxs-lookup"><span data-stu-id="d6c84-104">In this article, you will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="d6c84-105">Avant de poursuivre avec cet exemple, assurez-vous que vous avez installé l’ancrage, conformément au [Guide d’installation et de validation](xref:microsoft.quantum.chemistry.concepts.installation).</span><span class="sxs-lookup"><span data-stu-id="d6c84-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="d6c84-106">Pour plus d'informations :</span><span class="sxs-lookup"><span data-stu-id="d6c84-106">For more information:</span></span>
- [<span data-ttu-id="d6c84-107">Structure des ponts d’entrée NWChem</span><span class="sxs-lookup"><span data-stu-id="d6c84-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="d6c84-108">Commandes de pont d’entrée à utiliser avec le kit de développement quantique</span><span class="sxs-lookup"><span data-stu-id="d6c84-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [<span data-ttu-id="d6c84-109">Installation de la bibliothèque chimie et des dépendances</span><span class="sxs-lookup"><span data-stu-id="d6c84-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="d6c84-110">Comptage des ressources</span><span class="sxs-lookup"><span data-stu-id="d6c84-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="d6c84-111">Cet exemple nécessite l’exécution de Windows PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="d6c84-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="d6c84-112">Téléchargez PowerShell Core pour Windows, macOS ou Linux à l’adresse https://github.com/PowerShell/PowerShell .</span><span class="sxs-lookup"><span data-stu-id="d6c84-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="d6c84-113">Importation des modules PowerShell requis</span><span class="sxs-lookup"><span data-stu-id="d6c84-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="d6c84-114">Si vous ne l’avez pas déjà fait, clonez le [référentiel Microsoft/Quantum](https://github.com/Microsoft/Quantum), qui contient des exemples et des utilitaires pour travailler avec le kit de développement Quantum :</span><span class="sxs-lookup"><span data-stu-id="d6c84-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="d6c84-115">Une fois que vous avez cloné `Microsoft/Quantum` , effectuez une opération `cd` dans le `utilities/` dossier et importez le module PowerShell en vue d’une utilisation avec l’arrimeur et NWChem :</span><span class="sxs-lookup"><span data-stu-id="d6c84-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="d6c84-116">Par défaut, Windows empêche l’exécution de scripts ou de modules comme mesure de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d6c84-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="d6c84-117">Pour autoriser les modules tels que `Invoke-NWChem.psm1` à s’exécuter sous Windows, vous devrez peut-être modifier la stratégie d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d6c84-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="d6c84-118">Pour ce faire, exécutez la `Set-ExecutionPolicy` commande :</span><span class="sxs-lookup"><span data-stu-id="d6c84-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="d6c84-119">La stratégie d’exécution est ensuite rétablie lorsque vous quittez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6c84-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="d6c84-120">Si vous souhaitez enregistrer la stratégie d’exécution, utilisez une valeur différente pour `-Scope` :</span><span class="sxs-lookup"><span data-stu-id="d6c84-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="d6c84-121">La commande doit maintenant être `Convert-NWChemToBroombridge` disponible :</span><span class="sxs-lookup"><span data-stu-id="d6c84-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="d6c84-122">Ensuite, nous allons importer la `Get-GateCount` commande fournie avec l’exemple **GetGateCount** .</span><span class="sxs-lookup"><span data-stu-id="d6c84-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="d6c84-123">Pour plus d’informations, consultez les [instructions fournies avec l’exemple](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="d6c84-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount).</span></span>
<span data-ttu-id="d6c84-124">Ensuite, exécutez la commande suivante, en remplaçant `<runtime>` par `win10-x64` , `osx-x64` ou `linux-x64` , selon votre système d’exploitation :</span><span class="sxs-lookup"><span data-stu-id="d6c84-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="d6c84-125">La commande doit maintenant être `Get-GateCount` disponible :</span><span class="sxs-lookup"><span data-stu-id="d6c84-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="d6c84-126">Jeux d’entrée</span><span class="sxs-lookup"><span data-stu-id="d6c84-126">Input Decks</span></span> ##

<span data-ttu-id="d6c84-127">Le package NWChem prend un fichier texte appelé « _pont d’entrée_ » qui spécifie un problème de chimie quantique à résoudre, ainsi que d’autres paramètres tels que les paramètres d’allocation de mémoire.</span><span class="sxs-lookup"><span data-stu-id="d6c84-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="d6c84-128">Pour cet exemple, nous allons utiliser l’un des jeux de données prédéfinis fournis avec NWChem.</span><span class="sxs-lookup"><span data-stu-id="d6c84-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="d6c84-129">Tout d’abord, clonez le [référentiel nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):</span><span class="sxs-lookup"><span data-stu-id="d6c84-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="d6c84-130">Étant donné qu’il s’agit d’un référentiel très volumineux, nous pouvons effectuer un clone superficiel pour économiser de la bande passante et de l’espace disque à l’aide de l' `--depth 1` argument.</span><span class="sxs-lookup"><span data-stu-id="d6c84-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="d6c84-131">Toutefois, cette option est facultative.</span><span class="sxs-lookup"><span data-stu-id="d6c84-131">This is optional, however.</span></span>
> <span data-ttu-id="d6c84-132">Le clonage fonctionne parfaitement sans `--depth 1` .</span><span class="sxs-lookup"><span data-stu-id="d6c84-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="d6c84-133">Le `nwchemgit/nwchem` référentiel est fourni avec une série de jeux d’entrée destinés à être utilisés avec le kit de développement quantique, listé dans le [ `QA/chem_library_tests` dossier](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span><span class="sxs-lookup"><span data-stu-id="d6c84-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span></span>
<span data-ttu-id="d6c84-134">Pour cet exemple, nous allons utiliser le `H4` jeu d’entrée :</span><span class="sxs-lookup"><span data-stu-id="d6c84-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="d6c84-135">La molécule en question est un système de 4 atomes d’hydrogène organisés dans une certaine géométrie qui dépend d’un angle, le paramètre `alpha` comme indiqué dans le nom `h4_sto6g_alpha.nw` du pont.</span><span class="sxs-lookup"><span data-stu-id="d6c84-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="d6c84-136">H4 est un [test moléculaire](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) connu pour la chimie de calcul depuis les années 1970.</span><span class="sxs-lookup"><span data-stu-id="d6c84-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="d6c84-137">Le paramètre `sto6g` indique que le jeu met en œuvre une représentation en ce qui concerne un Slater orbital, en particulier une représentation par rapport à une [base arrêt-ng définie](https://en.wikipedia.org/wiki/STO-nG_basis_sets) avec 6 fonctions de base gaussienne.</span><span class="sxs-lookup"><span data-stu-id="d6c84-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="d6c84-138">Ce pont d’entrée contient en outre plusieurs instructions pour le NWChem tenseur Contracting Engine (TCE) qui dirige NWChem pour produire les informations nécessaires à l’interopérabilité avec le kit de développement Quantum :</span><span class="sxs-lookup"><span data-stu-id="d6c84-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="d6c84-139">Production et consommation de la sortie Broombridge à partir de NWChem</span><span class="sxs-lookup"><span data-stu-id="d6c84-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="d6c84-140">Vous disposez maintenant de tout ce dont vous avez besoin pour produire et consommer des documents Broombridge.</span><span class="sxs-lookup"><span data-stu-id="d6c84-140">You now have everything you need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="d6c84-141">Pour exécuter NWChem et produire un document Broombridge pour le `h4_sto6g_0.000.nw` jeu d’entrée, exécutez `Convert-NWChemToBroombridge` :</span><span class="sxs-lookup"><span data-stu-id="d6c84-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="d6c84-142">La première fois que vous exécutez cette commande, Dockr télécharge l' `nwchemorg/nwchem-qc` image pour vous.</span><span class="sxs-lookup"><span data-stu-id="d6c84-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="d6c84-143">Cela peut prendre un peu de temps, en fonction de la vitesse de votre connexion, ce qui vous donne la possibilité d’obtenir une tasse de café.</span><span class="sxs-lookup"><span data-stu-id="d6c84-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="d6c84-144">Cela produira un document Broombridge appelé `h4_sto6g_0.000.yaml` que vous pouvez utiliser avec `Get-GateCount` :</span><span class="sxs-lookup"><span data-stu-id="d6c84-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that you can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="d6c84-145">Vous devez maintenant voir la sortie de la console qui contient l’estimation des ressources, comme T-Count, le nombre de rotations, le nombre de CNOTIN, etc. pour diverses méthodes de simulation de Quantum :</span><span class="sxs-lookup"><span data-stu-id="d6c84-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="d6c84-146">Il y a beaucoup de choses à faire à partir d’ici :</span><span class="sxs-lookup"><span data-stu-id="d6c84-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="d6c84-147">Essayez différents jeux d’entrée prédéfinis, par exemple, en faisant varier le paramètre `alpha` dans `h4_sto6g_alpha.nw` ,</span><span class="sxs-lookup"><span data-stu-id="d6c84-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="d6c84-148">Essayez de modifier les ponts en modifiant directement les jeux NWChem, par exemple, en explorant les `STO-nG` modèles pour différents choix de n,</span><span class="sxs-lookup"><span data-stu-id="d6c84-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="d6c84-149">Essayez d’autres jeux d’entrée NWChem prédéfinis qui sont disponibles à l’adresse `nwchem/qa/chem_library_tests` ,</span><span class="sxs-lookup"><span data-stu-id="d6c84-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="d6c84-150">Essayez une suite de tests d’évaluation Broombridge YAML prédéfinis qui ont été générés à partir de NWChem et qui sont disponibles dans le cadre du [référentiel Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="d6c84-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="d6c84-151">Ces tests d’évaluation sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="d6c84-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="d6c84-152">petites molécules telles que l’hydrogène moléculaire (H2), le beryllium (a), le lithium-hydrure (LiH),</span><span class="sxs-lookup"><span data-stu-id="d6c84-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="d6c84-153">des molécules plus grandes telles que l’ozone (O3), bêta-carotène, cytosine et bien d’autres.</span><span class="sxs-lookup"><span data-stu-id="d6c84-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="d6c84-154">Essayez les flèches graphiques frontales [EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) qui intègrent une interface au Microsoft Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="d6c84-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="d6c84-155">Génération de la sortie Broombridge à partir de flèches EMSL</span><span class="sxs-lookup"><span data-stu-id="d6c84-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="d6c84-156">Pour vous familiariser avec les flèches EMSL front end basées sur le Web, accédez à un navigateur [ici](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span><span class="sxs-lookup"><span data-stu-id="d6c84-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="d6c84-157">L’exécution des flèches EMSL dans un navigateur Web requiert l’activation de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="d6c84-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="d6c84-158">Pour plus d’informations sur l’activation de JavaScript dans votre navigateur, reportez-vous à ces [instructions](https://www.enable-javascript.com/) .</span><span class="sxs-lookup"><span data-stu-id="d6c84-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="d6c84-159">Tout d’abord, entrez une molécule dans la zone de requête qui indique``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="d6c84-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="d6c84-160">Vous pouvez entrer de nombreuses molécules par leur nom commun, tel que « caféine » au lieu de « 1, 3, 7-Trimethylxanthine ».</span><span class="sxs-lookup"><span data-stu-id="d6c84-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="d6c84-161">Ensuite, cliquez sur le bouton qui indique ``theory{qsharp_chem}`` .</span><span class="sxs-lookup"><span data-stu-id="d6c84-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="d6c84-162">Cela remplira davantage la zone de requête avec une instruction qui indique à l’exécution d’exporter la sortie au format Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="d6c84-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="d6c84-163">À présent, Clock on ``Run Arrows`` .</span><span class="sxs-lookup"><span data-stu-id="d6c84-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="d6c84-164">Selon la taille de l’entrée, cette opération peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="d6c84-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="d6c84-165">Ou, au cas où le modèle particulier a déjà été calculé précédemment, il peut être fait extrêmement rapide, car il ne se limite qu’à une recherche dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="d6c84-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="d6c84-166">Dans les deux cas, vous êtes dirigé vers une nouvelle page qui contient une multitude d’informations sur l’exécution particulière de NWChem sur le jeu de données spécifié par votre entrée.</span><span class="sxs-lookup"><span data-stu-id="d6c84-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="d6c84-167">Vous pouvez télécharger et enregistrer le fichier Broombridge YAML à partir de la section qui commence par l’en-tête suivant :</span><span class="sxs-lookup"><span data-stu-id="d6c84-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="d6c84-168">Cliquez sur ``download`` , ce qui permet d’enregistrer une copie locale avec un nom de fichier unique, par exemple ``qsharp_chem48443.yaml`` (le nom particulier sera différent pour chaque exécution).</span><span class="sxs-lookup"><span data-stu-id="d6c84-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="d6c84-169">Vous pouvez ensuite traiter ce fichier comme indiqué ci-dessus, par exemple, avec</span><span class="sxs-lookup"><span data-stu-id="d6c84-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="d6c84-170">pour connaître le nombre de ressources.</span><span class="sxs-lookup"><span data-stu-id="d6c84-170">to get resource counts.</span></span> 

<span data-ttu-id="d6c84-171">Vous pouvez apprécier le générateur de molécules 3D accessible à partir de l' ``Arrows Entry - 3D Builder`` onglet sur la page de démarrage flèches EMSL.</span><span class="sxs-lookup"><span data-stu-id="d6c84-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="d6c84-172">Le fait de cliquer sur l’image 3D [JSMol](http://wiki.jmol.org/index.php/JSmol) de la molécule affichée vous permet de la modifier.</span><span class="sxs-lookup"><span data-stu-id="d6c84-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="d6c84-173">Vous pouvez déplacer des atomes, faire glisser des atomes pour que leurs distances inter-moléculaires changent, ajouter/supprimer des atomes, etc. Pour chacun de ces choix, une fois que vous avez ajouté ``theory{qsharp_chem}`` dans la zone de requête, vous pouvez générer une instance du schéma BROOMBRIDGE YAML et l’Explorer à l’aide de la bibliothèque de chimie Quantum.</span><span class="sxs-lookup"><span data-stu-id="d6c84-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
