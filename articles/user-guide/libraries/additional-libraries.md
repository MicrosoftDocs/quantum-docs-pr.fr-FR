---
title: Utilisation de Q# bibliothèques supplémentaires
description: Découvrez comment ajouter des Q# bibliothèques supplémentaires à vos applications Quantum.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869577"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="11cc0-103">Utilisation de Q# bibliothèques supplémentaires</span><span class="sxs-lookup"><span data-stu-id="11cc0-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="11cc0-104">Le kit de développement quantum fournit des fonctionnalités supplémentaires spécifiques au domaine via des _packages NuGet_ qui peuvent être ajoutés à vos Q# projets.</span><span class="sxs-lookup"><span data-stu-id="11cc0-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="11cc0-105">Q#Bibliothèque</span><span class="sxs-lookup"><span data-stu-id="11cc0-105">Q# Library</span></span>  | <span data-ttu-id="11cc0-106">Package NuGet</span><span class="sxs-lookup"><span data-stu-id="11cc0-106">NuGet package</span></span> | <span data-ttu-id="11cc0-107">Notes</span><span class="sxs-lookup"><span data-stu-id="11cc0-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="11cc0-108">Q#bibliothèque standard</span><span class="sxs-lookup"><span data-stu-id="11cc0-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="11cc0-109">**Microsoft. Quantum. standard**</span><span class="sxs-lookup"><span data-stu-id="11cc0-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="11cc0-110">Incluse par défaut</span><span class="sxs-lookup"><span data-stu-id="11cc0-110">Included by default</span></span> |
| [<span data-ttu-id="11cc0-111">Bibliothèque de chimie de quantum</span><span class="sxs-lookup"><span data-stu-id="11cc0-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="11cc0-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="11cc0-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="11cc0-113">Bibliothèque de valeurs numériques de quantum</span><span class="sxs-lookup"><span data-stu-id="11cc0-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="11cc0-114">**Microsoft. Quantum. Numerics**</span><span class="sxs-lookup"><span data-stu-id="11cc0-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="11cc0-115">Bibliothèque de Machine Learning quantique</span><span class="sxs-lookup"><span data-stu-id="11cc0-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="11cc0-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="11cc0-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="11cc0-117">Une fois que vous avez installé le kit de développement Quantum pour une utilisation avec votre environnement et votre langue d’hôte préférés, vous pouvez facilement ajouter des bibliothèques à des Q# projets individuels sans aucune autre installation.</span><span class="sxs-lookup"><span data-stu-id="11cc0-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="11cc0-118">Certaines Q# bibliothèques peuvent fonctionner correctement avec des outils supplémentaires qui fonctionnent Q# avec vos programmes ou qui s’intègrent à vos applications hôtes.</span><span class="sxs-lookup"><span data-stu-id="11cc0-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="11cc0-119">Par exemple, les [instructions d’installation de la bibliothèque chimie](xref:microsoft.quantum.chemistry.concepts.installation) décrivent comment utiliser le [package **Microsoft. Quantum. chimie** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) avec la plateforme de calcul de la chimie NWChem et comment installer les `qdk-chem` outils en ligne de commande pour l’utilisation des données de la chimie quantique.</span><span class="sxs-lookup"><span data-stu-id="11cc0-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[<span data-ttu-id="11cc0-120">Q#applications en ligne de commande ou .NET Interop</span><span class="sxs-lookup"><span data-stu-id="11cc0-120">Q# command-line applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="11cc0-121">**Ligne de commande ou Visual Studio code :** En utilisant la ligne de commande seule ou dans Visual Studio Code, vous pouvez utiliser la `dotnet` commande pour ajouter une référence de package NuGet à votre projet.</span><span class="sxs-lookup"><span data-stu-id="11cc0-121">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="11cc0-122">Par exemple, pour ajouter le package [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="11cc0-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="11cc0-123">**Visual Studio :** Si vous utilisez Visual Studio 2019 ou une version ultérieure, vous pouvez ajouter des Q# packages supplémentaires à l’aide du gestionnaire de package NuGet.</span><span class="sxs-lookup"><span data-stu-id="11cc0-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="11cc0-124">Pour charger un package :</span><span class="sxs-lookup"><span data-stu-id="11cc0-124">To load a package:</span></span> 
1. <span data-ttu-id="11cc0-125">Avec un projet ouvert dans Visual Studio, sélectionnez **gérer les packages NuGet...** dans le menu **projet** .</span><span class="sxs-lookup"><span data-stu-id="11cc0-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="11cc0-126">Cliquez sur **Parcourir**, sélectionnez **inclure la version préliminaire** et recherchez le nom du package « Microsoft. Quantum. Numerics ».</span><span class="sxs-lookup"><span data-stu-id="11cc0-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="11cc0-127">Cela permet de répertorier les packages disponibles au téléchargement.</span><span class="sxs-lookup"><span data-stu-id="11cc0-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="11cc0-128">Pointez sur **Microsoft. Quantum. Numerics** , puis cliquez sur la flèche pointant vers le bas à droite du numéro de version pour installer le package de valeurs numériques.</span><span class="sxs-lookup"><span data-stu-id="11cc0-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="11cc0-129">Pour plus d’informations, consultez le Guide de l' [interface utilisateur du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="11cc0-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="11cc0-130">Vous pouvez également utiliser la console du gestionnaire de package pour ajouter la bibliothèque numérique à votre projet par le biais de l’interface de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="11cc0-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Utiliser la console du gestionnaire de package à partir de la ligne de commande](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="11cc0-132">À partir de la console du gestionnaire de package, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="11cc0-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="11cc0-133">Pour plus d’informations, consultez le Guide de la [console du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="11cc0-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="11cc0-134">Q#Blocs-notes</span><span class="sxs-lookup"><span data-stu-id="11cc0-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="11cc0-135">Vous pouvez rendre des packages supplémentaires disponibles pour une utilisation dans un Q# bloc-notes I à l’aide de la [ `%package` commande Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="11cc0-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="11cc0-136">Par exemple, pour ajouter le package [**Microsoft. Quantum. Numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) à utiliser dans un Q# bloc-notes I, exécutez la commande suivante dans une cellule de bloc-notes :</span><span class="sxs-lookup"><span data-stu-id="11cc0-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="11cc0-137">Après cette commande, le package est disponible pour toutes les cellules dans le bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="11cc0-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="11cc0-138">Pour rendre le package disponible à partir du Q# Code de l’espace de travail actuel, rechargez l’espace de travail après avoir ajouté votre package :</span><span class="sxs-lookup"><span data-stu-id="11cc0-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="11cc0-139">Interopérabilité de Python</span><span class="sxs-lookup"><span data-stu-id="11cc0-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="11cc0-140">Vous pouvez rendre des packages supplémentaires disponibles pour une utilisation dans un programme hôte Python à l’aide de la [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) méthode.</span><span class="sxs-lookup"><span data-stu-id="11cc0-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="11cc0-141">Par exemple, pour ajouter le package [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) à utiliser dans un Q# Notebook I, exécutez le code python suivant :</span><span class="sxs-lookup"><span data-stu-id="11cc0-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="11cc0-142">Après cette commande, le package sera mis à la disposition de tout Q# code compilé à l’aide de `qsharp.compile` .</span><span class="sxs-lookup"><span data-stu-id="11cc0-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="11cc0-143">Pour rendre le package disponible à partir du Q# Code de l’espace de travail actuel, rechargez l’espace de travail après avoir ajouté votre package :</span><span class="sxs-lookup"><span data-stu-id="11cc0-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
