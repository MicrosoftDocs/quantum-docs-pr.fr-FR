---
title: 'Installation et validation de la bibliothèque Microsoft Q # chimie'
description: Apprenez à installer la bibliothèque Microsoft Quantum chimie et à l’utiliser avec la plateforme de calcul de calcul NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907356"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="050af-103">Installation et validation de la bibliothèque chimie</span><span class="sxs-lookup"><span data-stu-id="050af-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="050af-104">Le kit de développement Quantum prend en charge les applications de la chimie quantique par le biais du package NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .</span><span class="sxs-lookup"><span data-stu-id="050af-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="050af-105">Comme avec les autres packages NuGet, il est simple d’ajouter la bibliothèque chimie à votre projet.</span><span class="sxs-lookup"><span data-stu-id="050af-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="050af-106">**Visual Studio 2019 :** Si vous utilisez Visual Studio 2019, vous pouvez ajouter les packages de chimie des quantums à l’aide du gestionnaire de package NuGet.</span><span class="sxs-lookup"><span data-stu-id="050af-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="050af-107">Pour ouvrir le gestionnaire de package, cliquez avec le bouton droit sur le projet auquel vous souhaitez ajouter la bibliothèque de chimie, puis sélectionnez « gérer les packages NuGet... » comme dans la capture d’écran ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="050af-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![Utilisation du gestionnaire de package NuGet dans Visual Studio 2019](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="050af-109">Dans l’onglet Parcourir, recherchez le nom du package « Microsoft. Quantum. chimie ».</span><span class="sxs-lookup"><span data-stu-id="050af-109">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="050af-110">Veillez à cocher « inclure la version préliminaire ».</span><span class="sxs-lookup"><span data-stu-id="050af-110">Make sure to tick "Include prerelease."</span></span>

![Case à cocher inclure la version préliminaire](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="050af-112">Cela permet de répertorier les packages disponibles au téléchargement.</span><span class="sxs-lookup"><span data-stu-id="050af-112">This will list the packages available for download.</span></span>
<span data-ttu-id="050af-113">Cliquez sur « Microsoft. Quantum. chimie dans le volet gauche, sélectionnez la version préliminaire la plus récente dans le volet droit, puis cliquez sur «installer » :</span><span class="sxs-lookup"><span data-stu-id="050af-113">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![Installer le package Microsoft. Quantum. chimie le plus récent](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="050af-115">Pour plus d’informations, consultez le Guide de l' [interface utilisateur du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="050af-115">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="050af-116">Vous pouvez également utiliser la console du gestionnaire de package pour ajouter la bibliothèque de chimie Quantum à votre projet à l’aide d’une interface de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="050af-116">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![Utiliser la console du gestionnaire de package à partir de la ligne de commande](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="050af-118">À partir de la console du gestionnaire de package, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="050af-118">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="050af-119">Pour plus d’informations, consultez le Guide de la [console du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="050af-119">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="050af-120">**Ligne de commande ou Visual Studio code :** En utilisant la ligne de commande seule ou dans Visual Studio Code, vous pouvez utiliser la commande `dotnet` pour ajouter la référence de package NuGet à votre projet :</span><span class="sxs-lookup"><span data-stu-id="050af-120">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="050af-121">Vérification de votre installation</span><span class="sxs-lookup"><span data-stu-id="050af-121">Verifying Your Installation</span></span> 

<span data-ttu-id="050af-122">À l’instar du reste du kit de développement quantique, la bibliothèque Quantum chimie est fournie avec un certain nombre d’exemples entièrement documentés pour vous aider à devenir rapidement opérationnel.</span><span class="sxs-lookup"><span data-stu-id="050af-122">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="050af-123">Pour tester votre installation à l’aide de ces exemples, clonez le [référentiel d’exemples principal](https://github.com/Microsoft/Quantum), puis exécutez l’un des exemples.</span><span class="sxs-lookup"><span data-stu-id="050af-123">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="050af-124">Par exemple, pour exécuter l’exemple de [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) :</span><span class="sxs-lookup"><span data-stu-id="050af-124">For example, to run the [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="050af-125">Pour vérifier l’installation de la bibliothèque de chimie quantique à l’aide d’Microsoft Visual Studio après le clonage du référentiel :</span><span class="sxs-lookup"><span data-stu-id="050af-125">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="050af-126">Ouvrez la solution ChemistrySamples. sln dans le dossier chimie.</span><span class="sxs-lookup"><span data-stu-id="050af-126">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="050af-127">Sélectionnez Samples/1.</span><span class="sxs-lookup"><span data-stu-id="050af-127">Select Samples/1.</span></span> <span data-ttu-id="050af-128">Molécules/MolecularHydrogen simples comme projet de démarrage.</span><span class="sxs-lookup"><span data-stu-id="050af-128">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="050af-129">Appuyez sur F5 pour exécuter la démonstration de l’estimation de la phase Quantum d’hydrogène moléculaire.</span><span class="sxs-lookup"><span data-stu-id="050af-129">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="050af-130">Pour plus d’informations sur l’estimation des valeurs des niveaux d’énergie, consultez [obtention d’estimations au niveau](xref:microsoft.quantum.chemistry.examples.energyestimate) de l’énergie.</span><span class="sxs-lookup"><span data-stu-id="050af-130">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="050af-131">Utilisation du kit de développement quantique avec NWChem</span><span class="sxs-lookup"><span data-stu-id="050af-131">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="050af-132">L’exemple MolecularHydrogen utilise des données d’entrée moléculaires configurées manuellement.</span><span class="sxs-lookup"><span data-stu-id="050af-132">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="050af-133">Bien que cela soit parfait pour les petits exemples, la chimie quantique à l’échelle nécessite Hamiltonians avec des millions ou des milliards de termes.</span><span class="sxs-lookup"><span data-stu-id="050af-133">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="050af-134">Ces Hamiltonians, générés par des packages de chimie de calcul évolutif, sont trop volumineux pour être importés manuellement.</span><span class="sxs-lookup"><span data-stu-id="050af-134">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="050af-135">La bibliothèque Quantum chimie pour le kit de développement quantique est conçue pour fonctionner correctement avec les packages de chimie de calcul, notamment la plateforme de calcul de calcul [**NWChem**](http://www.nwchem-sw.org/) développée par le laboratoire Environmental-Sciences Environmental (EMSL) au laboratoire national du Nord-Ouest du Pacifique.</span><span class="sxs-lookup"><span data-stu-id="050af-135">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="050af-136">En particulier, le package `Microsoft.Quantum.Chemistry` fournit des outils pour le chargement d’instances de problèmes de simulation de la chimie Quantum représentés dans le [schéma Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), également pris en charge pour l’exportation par les versions récentes de NWChem.</span><span class="sxs-lookup"><span data-stu-id="050af-136">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="050af-137">Pour être opérationnel à l’aide de NWChem avec le kit de développement Quantum, nous vous suggérons l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="050af-137">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="050af-138">Commencez à utiliser les fichiers Broombridge existants fournis avec les exemples sur [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="050af-138">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="050af-139">Utilisez le [Générateur de flèches EMSL pour le Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) qui est un serveur frontal Web à NWChem pour générer de nouveaux fichiers d’entrée moléculaire avec format Broombridge.</span><span class="sxs-lookup"><span data-stu-id="050af-139">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="050af-140">Utilisez l' [image de l’arrimeur](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fournie par PNNL pour exécuter NWChem, ou</span><span class="sxs-lookup"><span data-stu-id="050af-140">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="050af-141">[Compilez NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) pour votre plateforme.</span><span class="sxs-lookup"><span data-stu-id="050af-141">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="050af-142">Pour plus d’informations sur l’utilisation de NWChem sur des modèles chimiques à des fins d’analyse avec la bibliothèque de modèles de développement quantique, consultez la page de [bout en bout avec NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) .</span><span class="sxs-lookup"><span data-stu-id="050af-142">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="050af-143">Prise en main des fichiers Broombridge fournis avec les exemples</span><span class="sxs-lookup"><span data-stu-id="050af-143">Getting started using Broombridge files provided with the samples</span></span>

<span data-ttu-id="050af-144">Le dossier [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) du référentiel d’exemples du kit de développement Quantum contient des fichiers de données de molécule en format Broombridge.</span><span class="sxs-lookup"><span data-stu-id="050af-144">The [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="050af-145">En guise d’exemple simple, utilisez l’exemple de bibliothèque chimie [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) pour charger le modèle Hamilton à partir de l’un des fichiers Broombridge et effectuer des estimations de la porte de la simulation de Quantum algorigthms :</span><span class="sxs-lookup"><span data-stu-id="050af-145">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="050af-146">Pour plus d’informations sur la façon d’entrer des molécules représentées par le schéma Broombridge, consultez chargement d’un modèle de niveau de données [à partir d’un fichier](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="050af-146">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="050af-147">Pour plus d’informations sur l’estimation des ressources, consultez [obtention du nombre de ressources](xref:microsoft.quantum.chemistry.examples.resourcecounts) .</span><span class="sxs-lookup"><span data-stu-id="050af-147">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="050af-148">Prise en main du générateur de flèches EMSL</span><span class="sxs-lookup"><span data-stu-id="050af-148">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="050af-149">EMSL Arrows est un outil qui utilise des bases de données de calcul NWChem et Chemical pour générer des données de molécule.</span><span class="sxs-lookup"><span data-stu-id="050af-149">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="050af-150">[Le générateur de flèches EMSL pour la Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) vous permet d’entrer votre modèle à l’aide de plusieurs générateurs de modèles moléculaires et de générer le fichier de fichier Broombridge à utiliser par le kit de développement quantique.</span><span class="sxs-lookup"><span data-stu-id="050af-150">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="050af-151">Dans la page EMSL, cliquez sur l’onglet ['instructions'] et suivez les instructions ['exemples simples'] pour générer des fichiers Broombridge.</span><span class="sxs-lookup"><span data-stu-id="050af-151">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="050af-152">Essayez ensuite d’exécuter ['GetGateCount'] pour voir les estimations de la ressource Quantum pour ces molécules.</span><span class="sxs-lookup"><span data-stu-id="050af-152">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="050af-153">Installation de NWChem à partir de la source</span><span class="sxs-lookup"><span data-stu-id="050af-153">Installing NWChem from Source</span></span>

<span data-ttu-id="050af-154">Des instructions complètes sur l’installation de NWChem à partir de la source [sont fournies par PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="050af-154">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="050af-155">Si vous souhaitez utiliser NWChem à partir de Windows 10, le sous-système Windows pour Linux est une option intéressante.</span><span class="sxs-lookup"><span data-stu-id="050af-155">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="050af-156">Une fois que vous avez installé [Ubuntu 18,04 LTS pour Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), exécutez `ubuntu18.04` à partir de votre terminal préféré et suivez les instructions ci-dessus pour installer NWChem à partir de la source.</span><span class="sxs-lookup"><span data-stu-id="050af-156">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="050af-157">Une fois que vous avez compilé NWChem à partir de la source, vous pouvez exécuter le script de `yaml_driver` fourni avec NWChem pour produire rapidement des instances Broombridge à partir de jeux d’entrée NWChem :</span><span class="sxs-lookup"><span data-stu-id="050af-157">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="050af-158">Cette commande crée un fichier de `input.yaml` au format Broombridge dans votre répertoire actif.</span><span class="sxs-lookup"><span data-stu-id="050af-158">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="050af-159">Utilisation de NWChem avec l’ancrage</span><span class="sxs-lookup"><span data-stu-id="050af-159">Using NWChem with Docker</span></span>

<span data-ttu-id="050af-160">Les images prédéfinies pour l’utilisation de NWChem sont disponibles sur plusieurs plateformes via le hub de l' [arrimeur](https://hub.docker.com).</span><span class="sxs-lookup"><span data-stu-id="050af-160">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="050af-161">Pour commencer, suivez les instructions d’installation de la station d’accueil pour votre plateforme :</span><span class="sxs-lookup"><span data-stu-id="050af-161">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="050af-162">Installer la station d’accueil pour Ubuntu</span><span class="sxs-lookup"><span data-stu-id="050af-162">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="050af-163">Installer l’arrimeur pour macOS</span><span class="sxs-lookup"><span data-stu-id="050af-163">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="050af-164">Installer Docker pour Windows 10</span><span class="sxs-lookup"><span data-stu-id="050af-164">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="050af-165">Si vous utilisez Docker pour Windows, vous devez partager le lecteur contenant votre répertoire temporaire (il s’agit généralement du lecteur `C:\`) avec le démon Dockr.</span><span class="sxs-lookup"><span data-stu-id="050af-165">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="050af-166">Pour plus d’informations, consultez la documentation de l' [ancrage](https://docs.docker.com/docker-for-windows/#shared-drives) .</span><span class="sxs-lookup"><span data-stu-id="050af-166">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="050af-167">Une fois que vous avez installé la station d’accueil, vous pouvez utiliser le module PowerShell fourni avec les exemples du kit de développement Quantum pour exécuter l’image, ou vous pouvez exécuter l’image manuellement.</span><span class="sxs-lookup"><span data-stu-id="050af-167">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="050af-168">Nous avons détaillé l’utilisation de PowerShell ici. Si vous souhaitez utiliser l’image de l’ancrer manuellement, consultez la [documentation fournie avec l’image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="050af-168">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="050af-169">Exécution de NWChem via PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="050af-169">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="050af-170">Pour utiliser l’image de l’Ancrable NWChem avec le kit de développement Quantum, nous fournissons un petit module PowerShell qui gère le déplacement des fichiers vers et depuis NWChem pour vous.</span><span class="sxs-lookup"><span data-stu-id="050af-170">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="050af-171">Si vous n’avez pas encore installé PowerShell Core, vous pouvez le télécharger sur plusieurs plateformes à partir du [référentiel PowerShell sur GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="050af-171">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="050af-172">PowerShell Core est également utilisé pour certains exemples pour démontrer l’interopérabilité avec les flux de travail de science des données et d’analyse commerciale.</span><span class="sxs-lookup"><span data-stu-id="050af-172">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="050af-173">Une fois PowerShell Core installé, importez `InvokeNWChem.psm1` pour rendre les commandes NWChem disponibles dans votre session active :</span><span class="sxs-lookup"><span data-stu-id="050af-173">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="050af-174">Cela rendra la commande `Convert-NWChemToBroombridge` disponible dans votre session PowerShell actuelle.</span><span class="sxs-lookup"><span data-stu-id="050af-174">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="050af-175">Pour télécharger les images nécessaires à partir de la station d’accueil et les utiliser pour exécuter des jeux d’entrée NWChem et capturer la sortie sur Broombridge, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="050af-175">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="050af-176">Cette opération crée un fichier Broombridge en exécutant NWChem sur `input.nw`.</span><span class="sxs-lookup"><span data-stu-id="050af-176">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="050af-177">Par défaut, la sortie Broombridge aura le même nom et le même chemin d’accès que le pont d’entrée, avec l’extension `.nw` remplacée par `.yaml`.</span><span class="sxs-lookup"><span data-stu-id="050af-177">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="050af-178">Cela peut être substitué à l’aide du paramètre `-DestinationPath` pour `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="050af-178">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="050af-179">Vous pouvez obtenir plus d’informations à l’aide des fonctionnalités d’aide intégrées de PowerShell :</span><span class="sxs-lookup"><span data-stu-id="050af-179">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
