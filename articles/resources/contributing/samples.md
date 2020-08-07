---
title: Contribution aux exemples Microsoft QDK
description: Apprenez à contribuer à l’exemple de code dans le Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 20da0e1765a242c172cc595f03d7791a0e8b8d2d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867506"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="8776e-103">Contribution des exemples au kit de développement quantique</span><span class="sxs-lookup"><span data-stu-id="8776e-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="8776e-104">Si vous souhaitez contribuer au code du référentiel d' [exemples](https://github.com/Microsoft/Quantum), Merci de faire de la communauté de développement quantique un meilleur endroit !</span><span class="sxs-lookup"><span data-stu-id="8776e-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="8776e-105">Référentiel d’exemples du kit de développement Quantum</span><span class="sxs-lookup"><span data-stu-id="8776e-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="8776e-106">Pour vous aider à préparer votre contribution pour vous aider dans la mesure du possible, il est utile d’examiner rapidement la disposition du référentiel d’exemples :</span><span class="sxs-lookup"><span data-stu-id="8776e-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="8776e-107">Autrement dit, les exemples du [référentiel Microsoft/Quantum](https://github.com/microsoft/Quantum) sont répartis par zone de sujet dans différents dossiers tels que `algorithms/` , `arithmetic/` ou `characterization/` .</span><span class="sxs-lookup"><span data-stu-id="8776e-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="8776e-108">Dans le dossier de chaque zone de sujet, chaque exemple se compose d’un dossier unique qui collecte tout ce dont l’utilisateur aura besoin pour explorer et utiliser cet exemple.</span><span class="sxs-lookup"><span data-stu-id="8776e-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="8776e-109">Structure des exemples</span><span class="sxs-lookup"><span data-stu-id="8776e-109">How Samples are Structured</span></span>

<span data-ttu-id="8776e-110">En examinant les fichiers qui composent chaque dossier, observons l' [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) exemple.</span><span class="sxs-lookup"><span data-stu-id="8776e-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="8776e-111">Fichier</span><span class="sxs-lookup"><span data-stu-id="8776e-111">File</span></span>              | <span data-ttu-id="8776e-112">Description</span><span class="sxs-lookup"><span data-stu-id="8776e-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="8776e-113">Q#projet utilisé pour générer l’exemple avec le kit SDK .NET Core</span><span class="sxs-lookup"><span data-stu-id="8776e-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="8776e-114">Q#opérations et fonctions pour l’exemple</span><span class="sxs-lookup"><span data-stu-id="8776e-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="8776e-115">Programme hôte C# utilisé pour exécuter l’exemple</span><span class="sxs-lookup"><span data-stu-id="8776e-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="8776e-116">Programme hôte python utilisé pour exécuter l’exemple</span><span class="sxs-lookup"><span data-stu-id="8776e-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="8776e-117">Documentation sur ce que fait l’exemple et comment l’utiliser</span><span class="sxs-lookup"><span data-stu-id="8776e-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="8776e-118">Tous les exemples n’auront pas exactement le même ensemble de fichiers (par exemple : certains exemples peuvent être en C# uniquement, d’autres peuvent ne pas avoir d’hôte python ou certains exemples peuvent nécessiter le fonctionnement de fichiers de données auxiliaires).</span><span class="sxs-lookup"><span data-stu-id="8776e-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="8776e-119">Anatomie d’un fichier Lisez-moi utile</span><span class="sxs-lookup"><span data-stu-id="8776e-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="8776e-120">Un fichier particulièrement important, cependant, est le `README.md` fichier, car c’est ce dont les utilisateurs ont besoin pour commencer à utiliser votre exemple !</span><span class="sxs-lookup"><span data-stu-id="8776e-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="8776e-121">Chaque `README.md` doit commencer par certaines métadonnées qui aident docs.Microsoft.com/samples à trouver votre contribution.</span><span class="sxs-lookup"><span data-stu-id="8776e-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8776e-122">Découvrez comment l’exemple CHSH-Game est rendu</span><span class="sxs-lookup"><span data-stu-id="8776e-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="8776e-123">Ces métadonnées sont fournies sous la forme d’un [en-tête YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) qui indique les langues que votre exemple couvre (en général, il s’agit de, `qsharp` `csharp` et `python` ), ainsi que des produits que votre exemple couvre (en général, simplement `qdk` ).</span><span class="sxs-lookup"><span data-stu-id="8776e-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="8776e-124">La `page_type: sample` clé dans l’en-tête est requise pour que votre exemple apparaisse dans docs.Microsoft.com/samples.</span><span class="sxs-lookup"><span data-stu-id="8776e-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="8776e-125">De même, les `product` `language` clés et sont essentielles pour aider les utilisateurs à trouver et exécuter votre exemple.</span><span class="sxs-lookup"><span data-stu-id="8776e-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="8776e-126">Après cela, il est utile de fournir une brève introduction qui indique ce que fait votre nouvel exemple :</span><span class="sxs-lookup"><span data-stu-id="8776e-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="8776e-127">Les utilisateurs de votre exemple apprécieront également de savoir ce dont ils ont besoin pour les exécuter (par exemple : les utilisateurs ont-ils uniquement besoin du kit de développement Quantum lui-même ou nécessitent-ils des logiciels supplémentaires tels que node.js ?) :</span><span class="sxs-lookup"><span data-stu-id="8776e-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="8776e-128">Tout cela étant en place, vous pouvez indiquer aux utilisateurs comment exécuter votre exemple :</span><span class="sxs-lookup"><span data-stu-id="8776e-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="8776e-129">Enfin, il est utile d’indiquer aux utilisateurs ce que fait chaque fichier de votre exemple, et où ils peuvent accéder pour plus d’informations :</span><span class="sxs-lookup"><span data-stu-id="8776e-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="8776e-130">Veillez à utiliser des URL absolues ici, car votre exemple apparaîtra dans une autre URL lorsqu’il sera rendu sur docs.microsoft.com/samples !</span><span class="sxs-lookup"><span data-stu-id="8776e-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
