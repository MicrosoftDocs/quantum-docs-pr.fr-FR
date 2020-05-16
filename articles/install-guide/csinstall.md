---
title: Développer avec Q# et .NET
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 155367dbb1373f00e2b0bd732a5319b32462c9f9
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426501"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="78ce3-102">Développer avec Q# et .NET</span><span class="sxs-lookup"><span data-stu-id="78ce3-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="78ce3-103">Q # est conçu pour fonctionner correctement avec les langages .NET tels que C# et F #.</span><span class="sxs-lookup"><span data-stu-id="78ce3-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="78ce3-104">Dans ce guide, nous allons montrer comment utiliser Q # avec un programme hôte écrit dans un langage .NET.</span><span class="sxs-lookup"><span data-stu-id="78ce3-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78ce3-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="78ce3-105">Prerequisites</span></span>

- <span data-ttu-id="78ce3-106">Installez le kit de développement Quantum [pour une utilisation avec des projets en ligne de commande Q #](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="78ce3-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="78ce3-107">Création d’une bibliothèque Q # et d’un hôte .NET</span><span class="sxs-lookup"><span data-stu-id="78ce3-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="78ce3-108">La première étape consiste à créer des projets pour votre bibliothèque Q #, et pour l’hôte .NET qui appellera les opérations et les fonctions définies dans votre bibliothèque Q #.</span><span class="sxs-lookup"><span data-stu-id="78ce3-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="78ce3-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="78ce3-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="78ce3-110">Créer une nouvelle bibliothèque Q #</span><span class="sxs-lookup"><span data-stu-id="78ce3-110">Create a new Q# library</span></span>
  - <span data-ttu-id="78ce3-111">Accéder au **fichier**  ->  **nouveau**  ->  **projet**</span><span class="sxs-lookup"><span data-stu-id="78ce3-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="78ce3-112">Tapez « Q # » dans la zone de recherche</span><span class="sxs-lookup"><span data-stu-id="78ce3-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="78ce3-113">Sélectionner la **bibliothèque Q #**</span><span class="sxs-lookup"><span data-stu-id="78ce3-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="78ce3-114">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="78ce3-114">Select **Next**</span></span>
  - <span data-ttu-id="78ce3-115">Choisir un nom et un emplacement pour votre bibliothèque</span><span class="sxs-lookup"><span data-stu-id="78ce3-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="78ce3-116">Vérifiez que l’option « Placer le projet et la solution dans le même répertoire » n’est pas **cochée** .</span><span class="sxs-lookup"><span data-stu-id="78ce3-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="78ce3-117">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="78ce3-117">Select **Create**</span></span>
- <span data-ttu-id="78ce3-118">Créer un nouveau programme hôte C# ou F #</span><span class="sxs-lookup"><span data-stu-id="78ce3-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="78ce3-119">Accédez à **fichier** → **nouveau** → **projet**</span><span class="sxs-lookup"><span data-stu-id="78ce3-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="78ce3-120">Sélectionnez « console App (.NET Core »)» pour C# ou F #</span><span class="sxs-lookup"><span data-stu-id="78ce3-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="78ce3-121">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="78ce3-121">Select **Next**</span></span>
  - <span data-ttu-id="78ce3-122">Sous *solution*, sélectionnez Ajouter à la solution.</span><span class="sxs-lookup"><span data-stu-id="78ce3-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="78ce3-123">Choisir un nom pour votre programme hôte</span><span class="sxs-lookup"><span data-stu-id="78ce3-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="78ce3-124">Sélectionnez **Créer**</span><span class="sxs-lookup"><span data-stu-id="78ce3-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="78ce3-125">Visual Studio Code ou ligne de commande</span><span class="sxs-lookup"><span data-stu-id="78ce3-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="78ce3-126">Créer une nouvelle bibliothèque Q #</span><span class="sxs-lookup"><span data-stu-id="78ce3-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="78ce3-127">Créer un projet de console C# ou F #</span><span class="sxs-lookup"><span data-stu-id="78ce3-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="78ce3-128">Ajoutez votre bibliothèque Q # en tant que référence à partir de votre programme hôte</span><span class="sxs-lookup"><span data-stu-id="78ce3-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="78ce3-129">Facultatif Créer une solution pour les deux projets</span><span class="sxs-lookup"><span data-stu-id="78ce3-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="78ce3-130">Appel de Q # à partir de .NET</span><span class="sxs-lookup"><span data-stu-id="78ce3-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="78ce3-131">Une fois vos projets configurés à l’issue des instructions ci-dessus, vous pouvez appeler Q # à partir de votre application console .NET.</span><span class="sxs-lookup"><span data-stu-id="78ce3-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="78ce3-132">Le compilateur Q # crée des classes .NET pour chaque opération et fonction Q # qui vous permettent d’exécuter vos programmes Quantum sur un simulateur.</span><span class="sxs-lookup"><span data-stu-id="78ce3-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="78ce3-133">Par exemple, l’exemple d' [interopérabilité .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) comprend l’exemple suivant d’une opération Q # :</span><span class="sxs-lookup"><span data-stu-id="78ce3-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="78ce3-134">Pour appeler cette opération à partir de .NET sur un simulateur Quantum, vous pouvez utiliser la `Run` méthode de la `RunAlgorithm` classe .net générée par le compilateur Q # :</span><span class="sxs-lookup"><span data-stu-id="78ce3-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="78ce3-135">C#</span><span class="sxs-lookup"><span data-stu-id="78ce3-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="78ce3-136">F#</span><span class="sxs-lookup"><span data-stu-id="78ce3-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="78ce3-137">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="78ce3-137">Next steps</span></span>

<span data-ttu-id="78ce3-138">Maintenant que vous avez configuré le kit de développement Quantum pour les deux programmes de ligne de commande Q # et pour l’interopérabilité avec .NET, vous pouvez écrire et exécuter [votre premier programme Quantum](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="78ce3-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
