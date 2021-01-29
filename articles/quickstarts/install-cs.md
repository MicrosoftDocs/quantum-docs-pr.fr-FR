---
title: Développer avec Q# et .NET
description: Découvrez comment créer une application Q# à l’aide de langages .NET.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: de79c361331766572f5608c341be766e071e01b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844303"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="56258-103">Développer avec Q# et .NET</span><span class="sxs-lookup"><span data-stu-id="56258-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="56258-104">Q# est conçu pour fonctionner avec les langages .NET tels que C# et F#.</span><span class="sxs-lookup"><span data-stu-id="56258-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="56258-105">Dans ce guide, nous allons vous montrer comment utiliser Q# avec un programme hôte écrit dans un langage .NET.</span><span class="sxs-lookup"><span data-stu-id="56258-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="56258-106">Tout d’abord, nous allons créer l’application Q# et l’hôte .NET, puis nous allons expliquer comment appeler le code Q# à partir de l’hôte.</span><span class="sxs-lookup"><span data-stu-id="56258-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56258-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="56258-107">Prerequisites</span></span>

- <span data-ttu-id="56258-108">Installez le kit de développement Quantum [pour l’utiliser avec les projets Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="56258-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="56258-109">Création d’une bibliothèque Q# et d’un hôte .NET</span><span class="sxs-lookup"><span data-stu-id="56258-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="56258-110">La première étape consiste à créer des projets pour votre bibliothèque Q# et pour l’hôte .NET qui appellera les opérations et les fonctions définies dans votre bibliothèque Q#.</span><span class="sxs-lookup"><span data-stu-id="56258-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="56258-111">Suivez les instructions situées sous l’onglet correspondant à votre environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="56258-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="56258-112">Si vous utilisez un éditeur autre que Visual Studio ou VS Code, suivez les étapes de l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="56258-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="56258-113">Visual Studio Code ou invite de commandes</span><span class="sxs-lookup"><span data-stu-id="56258-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="56258-114">Créer une bibliothèque Q#</span><span class="sxs-lookup"><span data-stu-id="56258-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="56258-115">Créer un projet console C# ou F#</span><span class="sxs-lookup"><span data-stu-id="56258-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="56258-116">Ajouter votre bibliothèque Q# comme référence à partir de votre programme hôte</span><span class="sxs-lookup"><span data-stu-id="56258-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="56258-117">[Facultatif] Créer une solution pour les deux projets</span><span class="sxs-lookup"><span data-stu-id="56258-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="56258-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="56258-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="56258-119">Créer une bibliothèque Q#</span><span class="sxs-lookup"><span data-stu-id="56258-119">Create a new Q# library</span></span>
  - <span data-ttu-id="56258-120">Accédez à **Fichier** -> **Nouveau** -> **Projet**</span><span class="sxs-lookup"><span data-stu-id="56258-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="56258-121">Saisissez « Q# » dans la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="56258-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="56258-122">Sélectionnez **Bibliothèque Q#** .</span><span class="sxs-lookup"><span data-stu-id="56258-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="56258-123">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="56258-123">Select **Next**</span></span>
  - <span data-ttu-id="56258-124">Choisissez un nom et un emplacement pour votre bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="56258-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="56258-125">Vérifiez que l’option « Placer la solution et le projet dans le même répertoire » est **décochée**.</span><span class="sxs-lookup"><span data-stu-id="56258-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="56258-126">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="56258-126">Select **Create**</span></span>
- <span data-ttu-id="56258-127">Créer un programme hôte C# ou F#</span><span class="sxs-lookup"><span data-stu-id="56258-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="56258-128">Accédez à **Fichier** → **Nouveau** → **Projet**.</span><span class="sxs-lookup"><span data-stu-id="56258-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="56258-129">Sélectionnez Application console (.NET Core) pour C# ou F#.</span><span class="sxs-lookup"><span data-stu-id="56258-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="56258-130">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="56258-130">Select **Next**</span></span>
  - <span data-ttu-id="56258-131">Sous *Solution*, sélectionnez Ajouter à la solution.</span><span class="sxs-lookup"><span data-stu-id="56258-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="56258-132">Choisissez un nom pour votre programme hôte.</span><span class="sxs-lookup"><span data-stu-id="56258-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="56258-133">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="56258-133">Select **Create**</span></span>

<span data-ttu-id="56258-134">\*\*_</span><span class="sxs-lookup"><span data-stu-id="56258-134">\*\*_</span></span>

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="56258-135">Appel de Q# à partir de .NET</span><span class="sxs-lookup"><span data-stu-id="56258-135">Calling into Q# from .NET</span></span>

<span data-ttu-id="56258-136">Une fois vos projets configurés à l’aide des instructions ci-dessus, vous pouvez appeler Q# à partir de votre application console .NET.</span><span class="sxs-lookup"><span data-stu-id="56258-136">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="56258-137">Le compilateur Q# crée des classes .NET pour chaque opération et fonction Q# qui vous permettent d’exécuter vos programmes quantiques sur un simulateur.</span><span class="sxs-lookup"><span data-stu-id="56258-137">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="56258-138">Par exemple, l’[exemple d’interopérabilité .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) comprend l’exemple suivant d’une opération Q# :</span><span class="sxs-lookup"><span data-stu-id="56258-138">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="56258-139">Pour appeler cette opération à partir de .NET sur un simulateur quantique, vous pouvez utiliser la méthode `Run` de la classe .NET `RunAlgorithm` générée par le compilateur Q# :</span><span class="sxs-lookup"><span data-stu-id="56258-139">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="56258-140">C#</span><span class="sxs-lookup"><span data-stu-id="56258-140">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="56258-141">F#</span><span class="sxs-lookup"><span data-stu-id="56258-141">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

<span data-ttu-id="56258-142">_\*\*</span><span class="sxs-lookup"><span data-stu-id="56258-142">_\*\*</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="56258-143">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="56258-143">Next steps</span></span>

<span data-ttu-id="56258-144">Maintenant que vous avez configuré le kit de développement Quantum pour les deux applications Q# et pour l’interopérabilité avec .NET, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="56258-144">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
