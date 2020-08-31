---
title: Développer avec Q# et .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 24318380e0e63957a51961762a33446fe0121b21
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863672"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="e18c3-102">Développer avec Q# et .NET</span><span class="sxs-lookup"><span data-stu-id="e18c3-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="e18c3-103">Q# est conçu pour fonctionner avec les langages .NET tels que C# et F#.</span><span class="sxs-lookup"><span data-stu-id="e18c3-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="e18c3-104">Dans ce guide, nous allons vous montrer comment utiliser Q# avec un programme hôte écrit dans un langage .NET.</span><span class="sxs-lookup"><span data-stu-id="e18c3-104">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="e18c3-105">Tout d’abord, nous allons créer l’application Q# et l’hôte .NET, puis nous allons expliquer comment appeler le code Q# à partir de l’hôte.</span><span class="sxs-lookup"><span data-stu-id="e18c3-105">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e18c3-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="e18c3-106">Prerequisites</span></span>

- <span data-ttu-id="e18c3-107">Installez le kit de développement Quantum [pour l’utiliser avec les projets Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="e18c3-107">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="e18c3-108">Création d’une bibliothèque Q# et d’un hôte .NET</span><span class="sxs-lookup"><span data-stu-id="e18c3-108">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="e18c3-109">La première étape consiste à créer des projets pour votre bibliothèque Q# et pour l’hôte .NET qui appellera les opérations et les fonctions définies dans votre bibliothèque Q#.</span><span class="sxs-lookup"><span data-stu-id="e18c3-109">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="e18c3-110">Suivez les instructions situées sous l’onglet correspondant à votre environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="e18c3-110">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="e18c3-111">Si vous utilisez un éditeur autre que Visual Studio ou VS Code, suivez les étapes de l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="e18c3-111">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="e18c3-112">Visual Studio Code ou invite de commandes</span><span class="sxs-lookup"><span data-stu-id="e18c3-112">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="e18c3-113">Créer une bibliothèque Q#</span><span class="sxs-lookup"><span data-stu-id="e18c3-113">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="e18c3-114">Créer un projet console C# ou F#</span><span class="sxs-lookup"><span data-stu-id="e18c3-114">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="e18c3-115">Ajouter votre bibliothèque Q# comme référence à partir de votre programme hôte</span><span class="sxs-lookup"><span data-stu-id="e18c3-115">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="e18c3-116">[Facultatif] Créer une solution pour les deux projets</span><span class="sxs-lookup"><span data-stu-id="e18c3-116">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="e18c3-117">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e18c3-117">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="e18c3-118">Créer une bibliothèque Q#</span><span class="sxs-lookup"><span data-stu-id="e18c3-118">Create a new Q# library</span></span>
  - <span data-ttu-id="e18c3-119">Accédez à **Fichier** -> **Nouveau** -> **Projet**</span><span class="sxs-lookup"><span data-stu-id="e18c3-119">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="e18c3-120">Saisissez « Q# » dans la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="e18c3-120">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="e18c3-121">Sélectionnez **Bibliothèque Q#** .</span><span class="sxs-lookup"><span data-stu-id="e18c3-121">Select **Q# Library**</span></span>
  - <span data-ttu-id="e18c3-122">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e18c3-122">Select **Next**</span></span>
  - <span data-ttu-id="e18c3-123">Choisissez un nom et un emplacement pour votre bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="e18c3-123">Choose a name and location for your library</span></span>
  - <span data-ttu-id="e18c3-124">Vérifiez que l’option « Placer la solution et le projet dans le même répertoire » est **décochée**.</span><span class="sxs-lookup"><span data-stu-id="e18c3-124">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="e18c3-125">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="e18c3-125">Select **Create**</span></span>
- <span data-ttu-id="e18c3-126">Créer un programme hôte C# ou F#</span><span class="sxs-lookup"><span data-stu-id="e18c3-126">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="e18c3-127">Accédez à **Fichier** → **Nouveau** → **Projet**.</span><span class="sxs-lookup"><span data-stu-id="e18c3-127">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="e18c3-128">Sélectionnez Application console (.NET Core) pour C# ou F#.</span><span class="sxs-lookup"><span data-stu-id="e18c3-128">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="e18c3-129">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e18c3-129">Select **Next**</span></span>
  - <span data-ttu-id="e18c3-130">Sous *Solution*, sélectionnez Ajouter à la solution.</span><span class="sxs-lookup"><span data-stu-id="e18c3-130">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="e18c3-131">Choisissez un nom pour votre programme hôte.</span><span class="sxs-lookup"><span data-stu-id="e18c3-131">Choose a name for your host program</span></span>
  - <span data-ttu-id="e18c3-132">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="e18c3-132">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="e18c3-133">Appel de Q# à partir de .NET</span><span class="sxs-lookup"><span data-stu-id="e18c3-133">Calling into Q# from .NET</span></span>

<span data-ttu-id="e18c3-134">Une fois vos projets configurés à l’aide des instructions ci-dessus, vous pouvez appeler Q# à partir de votre application console .NET.</span><span class="sxs-lookup"><span data-stu-id="e18c3-134">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="e18c3-135">Le compilateur Q# crée des classes .NET pour chaque opération et fonction Q# qui vous permettent d’exécuter vos programmes quantiques sur un simulateur.</span><span class="sxs-lookup"><span data-stu-id="e18c3-135">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="e18c3-136">Par exemple, l’[exemple d’interopérabilité .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) comprend l’exemple suivant d’une opération Q# :</span><span class="sxs-lookup"><span data-stu-id="e18c3-136">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="e18c3-137">Pour appeler cette opération à partir de .NET sur un simulateur quantique, vous pouvez utiliser la méthode `Run` de la classe .NET `RunAlgorithm` générée par le compilateur Q# :</span><span class="sxs-lookup"><span data-stu-id="e18c3-137">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="e18c3-138">C#</span><span class="sxs-lookup"><span data-stu-id="e18c3-138">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="e18c3-139">F#</span><span class="sxs-lookup"><span data-stu-id="e18c3-139">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="e18c3-140">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="e18c3-140">Next steps</span></span>

<span data-ttu-id="e18c3-141">Maintenant que vous avez configuré le kit de développement Quantum pour les deux applications Q# et pour l’interopérabilité avec .NET, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="e18c3-141">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
