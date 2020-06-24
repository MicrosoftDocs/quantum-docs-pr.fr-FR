---
title: Bibliothèque de valeurs numériques Quantum Microsoft-installation et validation
description: Découvrez comment ajouter la bibliothèque de valeurs numériques Quantum Microsoft à votre installation de Visual Studio 2019 ou version ultérieure.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275188"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="403e3-103">Installation et validation de la bibliothèque de valeurs numériques</span><span class="sxs-lookup"><span data-stu-id="403e3-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="403e3-104">Le kit de développement Quantum prend en charge les fonctionnalités numériques via le [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package NuGet.</span><span class="sxs-lookup"><span data-stu-id="403e3-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="403e3-105">**>Visual Studio = 2019 :** Si vous utilisez Visual Studio 2019 ou une version ultérieure, vous pouvez ajouter le package de valeurs numériques à l’aide du gestionnaire de package NuGet.</span><span class="sxs-lookup"><span data-stu-id="403e3-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="403e3-106">Pour ce faire, sélectionnez « gérer les packages NuGet... ». à partir de l’élément de menu « projet » dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="403e3-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="403e3-107">Dans l’onglet Parcourir, recherchez le nom du package « Microsoft. Quantum. Numerics ».</span><span class="sxs-lookup"><span data-stu-id="403e3-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="403e3-108">Veillez à cocher « inclure la version préliminaire »</span><span class="sxs-lookup"><span data-stu-id="403e3-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="403e3-109">Cela permet de répertorier les packages disponibles au téléchargement.</span><span class="sxs-lookup"><span data-stu-id="403e3-109">This will list the packages available for download.</span></span>
<span data-ttu-id="403e3-110">Le fait de pointer sur « Microsoft. Quantum. Numerics » révèle une flèche pointant vers le bas à droite du numéro de version.</span><span class="sxs-lookup"><span data-stu-id="403e3-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="403e3-111">Cliquez sur la flèche pour installer le package numérique.</span><span class="sxs-lookup"><span data-stu-id="403e3-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="403e3-112">Pour plus d’informations, consultez le Guide de l' [interface utilisateur du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="403e3-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="403e3-113">Vous pouvez également utiliser la console du gestionnaire de package pour ajouter la bibliothèque numérique à votre projet par le biais de l’interface de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="403e3-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Utiliser la console du gestionnaire de package à partir de la ligne de commande](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="403e3-115">À partir de la console du gestionnaire de package, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="403e3-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="403e3-116">Pour plus d’informations, consultez le Guide de la [console du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="403e3-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="403e3-117">**Ligne de commande ou Visual Studio code :** En utilisant la ligne de commande seule ou dans Visual Studio Code, vous pouvez utiliser la `dotnet` commande pour ajouter la référence de package NuGet à votre projet :</span><span class="sxs-lookup"><span data-stu-id="403e3-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="403e3-118">Vérification de votre installation</span><span class="sxs-lookup"><span data-stu-id="403e3-118">Verifying your installation</span></span>

<span data-ttu-id="403e3-119">À l’instar du reste du kit de développement quantique, la bibliothèque de valeurs numériques est fournie avec des exemples qui vous aident à démarrer aussi rapidement que possible.</span><span class="sxs-lookup"><span data-stu-id="403e3-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="403e3-120">Pour tester votre installation à l’aide de ces exemples, clonez le [référentiel d’exemples principal](https://github.com/Microsoft/Quantum) , puis exécutez l’un des exemples.</span><span class="sxs-lookup"><span data-stu-id="403e3-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="403e3-121">Pour exécuter l' [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) exemple :</span><span class="sxs-lookup"><span data-stu-id="403e3-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
