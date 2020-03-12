---
title: Contribution du code à Microsoft QDK
description: Apprenez à contribuer à l’exemple de code de bibliothèque et à l’Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022467"
---
# <a name="contributing-code"></a><span data-ttu-id="94649-103">Code de contribution</span><span class="sxs-lookup"><span data-stu-id="94649-103">Contributing Code</span></span>

<span data-ttu-id="94649-104">Outre la création de rapports sur les problèmes et l’amélioration de la documentation, le code du kit de développement quantique peut être un moyen très direct d’aider vos pairs dans la communauté de programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="94649-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="94649-105">En faisant contribution du code, vous pouvez aider à résoudre les problèmes, à fournir de nouveaux exemples, à rendre les bibliothèques existantes plus faciles à utiliser, voire à ajouter des fonctionnalités entièrement nouvelles.</span><span class="sxs-lookup"><span data-stu-id="94649-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="94649-106">Dans ce guide, nous allons détailler un peu ce que nous cherchons lorsque nous examinerons des demandes de tirage pour aider votre contribution à faire le meilleur.</span><span class="sxs-lookup"><span data-stu-id="94649-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="94649-107">Ce que nous recherchons</span><span class="sxs-lookup"><span data-stu-id="94649-107">What We Look For</span></span>

<span data-ttu-id="94649-108">Une contribution de code idéale s’appuie sur le travail existant dans un référentiel de kit de développement quantique pour résoudre les problèmes, étendre les fonctionnalités existantes ou ajouter de nouvelles fonctionnalités dans l’étendue d’un référentiel.</span><span class="sxs-lookup"><span data-stu-id="94649-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="94649-109">Lorsque nous acceptons une contribution au code, elle devient une partie du kit de développement quantique proprement dit, de sorte que les nouvelles fonctionnalités seront publiées, gérées et développées de la même façon que le reste du kit de développement quantique.</span><span class="sxs-lookup"><span data-stu-id="94649-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="94649-110">Par conséquent, il est utile lorsque la fonctionnalité ajoutée par une contribution est bien testée et est documentée.</span><span class="sxs-lookup"><span data-stu-id="94649-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="94649-111">tests unitaires</span><span class="sxs-lookup"><span data-stu-id="94649-111">Unit Tests</span></span>

<span data-ttu-id="94649-112">Les fonctions Q #, les opérations et les types définis par l’utilisateur qui composent les bibliothèques comme Canon sont testés automatiquement dans le cadre du développement sur le référentiel [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .</span><span class="sxs-lookup"><span data-stu-id="94649-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="94649-113">Lors de l’ouverture d’une nouvelle demande de tirage (pull request), par exemple, notre configuration de [Azure pipelines](https://azure.microsoft.com/services/devops/pipelines/) vérifie que les modifications apportées à la requête de tirage n’interrompent pas les fonctionnalités existantes dont dépend la communauté de programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="94649-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="94649-114">Avec la dernière version de Q #, le test unitaire est défini à l’aide de l’attribut `@Test("QuantumSimulator")`.</span><span class="sxs-lookup"><span data-stu-id="94649-114">With the latest Q# version, unit test are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="94649-115">L’argument peut être soit « QuantumSimulator », « ToffoliSimulator », « TraceSimulator », soit un nom qualifié complet spécifiant la cible d’exécution.</span><span class="sxs-lookup"><span data-stu-id="94649-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the execution target.</span></span> <span data-ttu-id="94649-116">Plusieurs attributs définissant différentes cibles d’exécution peuvent être attachés au même appelable.</span><span class="sxs-lookup"><span data-stu-id="94649-116">Several attributes defining different execution targets may be attached to the same callable.</span></span> <span data-ttu-id="94649-117">Certains de nos tests utilisent toujours le package [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) déconseillé qui expose toutes les fonctions Q # et les opérations se terminant par `Test` à l’infrastructure [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="94649-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="94649-118">Ce package n’est plus nécessaire pour définir des tests unitaires.</span><span class="sxs-lookup"><span data-stu-id="94649-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="94649-119">La fonction suivante est utilisée pour garantir que les fonctions <xref:microsoft.quantum.canon.fst> et <xref:microsoft.quantum.canon.snd> retournent les sorties de droite dans un exemple représentatif.</span><span class="sxs-lookup"><span data-stu-id="94649-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="94649-120">Si la sortie de `Fst` ou `Snd` est incorrecte, l’instruction `fail` est utilisée pour provoquer l’échec du test.</span><span class="sxs-lookup"><span data-stu-id="94649-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="94649-121">Des conditions plus complexes peuvent être vérifiées à l’aide des techniques décrites dans la [section Test](xref:microsoft.quantum.libraries.diagnostics) du Guide des bibliothèques standard.</span><span class="sxs-lookup"><span data-stu-id="94649-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="94649-122">Par exemple, le test suivant vérifie que `H(q); X(q); H(q);` comme appelé par <xref:microsoft.quantum.canon.applywith> fait la même chose que `Z(q)`.</span><span class="sxs-lookup"><span data-stu-id="94649-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="94649-123">Quand vous ajoutez de nouvelles fonctionnalités, il est judicieux d’ajouter également de nouveaux tests pour vous assurer que votre contribution fait ce qu’elle est supposée.</span><span class="sxs-lookup"><span data-stu-id="94649-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="94649-124">Cela aide le reste de la communauté à gérer et à développer votre fonctionnalité, et en particulier permet à d’autres développeurs de savoir qu’ils peuvent compter sur votre fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="94649-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="94649-125">Cela fonctionne également dans l’autre sens.</span><span class="sxs-lookup"><span data-stu-id="94649-125">This works the other way around, too!</span></span>
> <span data-ttu-id="94649-126">S’il existe une fonctionnalité qui ne contient pas de tests, nous vous aidons à ajouter la couverture de test, ce qui contribuera à la communauté.</span><span class="sxs-lookup"><span data-stu-id="94649-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="94649-127">Localement, les tests unitaires peuvent être exécutés à l’aide de l’Explorateur de tests Visual Studio ou de la commande `dotnet test`, afin que vous puissiez vérifier votre contribution avant d’ouvrir une demande de tirage (pull request).</span><span class="sxs-lookup"><span data-stu-id="94649-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="94649-128">Lors du rejet d’une requête de tirage</span><span class="sxs-lookup"><span data-stu-id="94649-128">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="94649-129">Parfois, nous rejetterons la demande de tirage (pull request) pour une contribution.</span><span class="sxs-lookup"><span data-stu-id="94649-129">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="94649-130">Si cela se produit, cela ne signifie pas qu’il est mauvais, car il existe un certain nombre de raisons pour lesquelles nous pouvons ne pas être en mesure d’accepter une contribution particulière.</span><span class="sxs-lookup"><span data-stu-id="94649-130">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="94649-131">Le plus souvent, une contribution à la communauté de programmation quantique est très bonne, mais les référentiels du kit de développement quantique ne sont pas le bon endroit pour le développer.</span><span class="sxs-lookup"><span data-stu-id="94649-131">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="94649-132">Dans ce cas, nous vous encourageons fortement à créer votre propre référentiel---partie de la force du kit de développement quantique, c’est qu’il est facile de créer et de distribuer vos propres bibliothèques à l’aide de GitHub et NuGet.org, de la même façon que nous distribuons l’Canon et la chimie bibliothèques actuelles.</span><span class="sxs-lookup"><span data-stu-id="94649-132">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="94649-133">À d’autres moments, nous pouvons rejeter une bonne contribution simplement parce que nous ne sommes pas encore prêts à le maintenir et à le développer.</span><span class="sxs-lookup"><span data-stu-id="94649-133">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="94649-134">Il peut être difficile de faire tout, donc nous prévoyons les fonctionnalités sur lesquelles nous sommes le plus à même de travailler dans le cadre d’une feuille de route.</span><span class="sxs-lookup"><span data-stu-id="94649-134">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="94649-135">Il peut s’agir d’un autre cas dans lequel la publication d’une fonctionnalité en tant que bibliothèque tierce peut s’avérer très utile.</span><span class="sxs-lookup"><span data-stu-id="94649-135">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="94649-136">Vous pouvez également demander de l’aide pour modifier une fonctionnalité afin qu’elle s’adapte mieux à notre feuille de route afin que nous puissions faire le meilleur travail possible.</span><span class="sxs-lookup"><span data-stu-id="94649-136">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="94649-137">Nous vous demanderons également les modifications apportées à une demande de tirage (pull request) si elle nécessite davantage de documentation ou de tests unitaires pour nous aider à l’utiliser, ou si elle diffère du style des autres bibliothèques Q # qu’il est plus difficile pour les utilisateurs de trouver votre fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="94649-137">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="94649-138">Dans ces cas-là, nous allons essayer de proposer des avis de code sur les éléments qui peuvent être ajoutés ou modifiés pour faciliter l’inclusion de votre contribution.</span><span class="sxs-lookup"><span data-stu-id="94649-138">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="94649-139">Enfin, nous ne pouvons pas accepter les contributions qui causent un préjudice à la communauté de quantum computing, comme indiqué dans le [Code de réalisation de Microsoft Open source](https://opensource.microsoft.com/codeofconduct/).</span><span class="sxs-lookup"><span data-stu-id="94649-139">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="94649-140">Nous voulons nous assurer que les contributions servent l’ensemble de la communauté de calcul Quantum, à la fois dans sa grande diversité et dans le futur, à mesure qu’elle s’étendra pour devenir encore plus inclusive.</span><span class="sxs-lookup"><span data-stu-id="94649-140">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="94649-141">Nous apprécions votre aide pour la réalisation de cet objectif.</span><span class="sxs-lookup"><span data-stu-id="94649-141">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94649-142">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="94649-142">Next steps</span></span>

<span data-ttu-id="94649-143">Merci d’avoir aidé à faire de la communauté de développement quantique une formidable ressource pour l’ensemble de la communauté de programmation quantique !</span><span class="sxs-lookup"><span data-stu-id="94649-143">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="94649-144">Pour plus d’informations, consultez le guide suivant sur le style Q #.</span><span class="sxs-lookup"><span data-stu-id="94649-144">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94649-145">En savoir plus sur les directives de style Q #</span><span class="sxs-lookup"><span data-stu-id="94649-145">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="94649-146">Selon le type de code que vous contribuez, il peut y avoir des éléments supplémentaires à garder à l’esprit qui peuvent vous aider à faire en sorte que votre contribution fasse autant de choses que possible pour la communauté.</span><span class="sxs-lookup"><span data-stu-id="94649-146">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94649-147">En savoir plus sur les exemples contributeurs</span><span class="sxs-lookup"><span data-stu-id="94649-147">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
