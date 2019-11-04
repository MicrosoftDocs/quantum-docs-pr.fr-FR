---
title: Ouverture des requêtes de tirage | Microsoft Docs
description: Ouverture des requêtes de tirage
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: d70a0a0319d14cfdae4910b897733d77b236f2f9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183724"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="d1233-103">Ouverture des requêtes de tirage</span><span class="sxs-lookup"><span data-stu-id="d1233-103">Opening Pull Requests</span></span> #

<span data-ttu-id="d1233-104">Toute la documentation du kit de développement Quantum est gérée à l’aide du système de contrôle de version git via l’utilisation de plusieurs dépôts hébergés sur GitHub.</span><span class="sxs-lookup"><span data-stu-id="d1233-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="d1233-105">L’utilisation conjointe de git et de GitHub facilite la collaboration sur le kit de développement quantique.</span><span class="sxs-lookup"><span data-stu-id="d1233-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="d1233-106">En particulier, tous les référentiels git peuvent être clonés ou dupliqués pour créer une copie totalement indépendante de ce référentiel.</span><span class="sxs-lookup"><span data-stu-id="d1233-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="d1233-107">Cela vous permet de travailler sur votre contribution avec les outils et à un rythme que vous préférez.</span><span class="sxs-lookup"><span data-stu-id="d1233-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="d1233-108">Lorsque vous êtes prêt, vous pouvez nous envoyer une demande pour inclure votre contribution dans nos dépôts, à l’aide de la fonctionnalité de _demande de tirage (pull Request_ ) de github.</span><span class="sxs-lookup"><span data-stu-id="d1233-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="d1233-109">La page de chaque demande de tirage comprend les détails de toutes les modifications qui apportent votre contribution, une liste de commentaires sur votre contribution et un ensemble d’outils de révision que les autres membres de la Communauté peuvent utiliser pour fournir des commentaires et des conseils.</span><span class="sxs-lookup"><span data-stu-id="d1233-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="d1233-110">Bien qu’un didacticiel complet sur git dépasse le cadre de ce guide, nous pouvons suggérer les liens suivants pour obtenir plus de ressources sur la formation git :</span><span class="sxs-lookup"><span data-stu-id="d1233-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="d1233-111">[Découvrez git](https://www.atlassian.com/git): un ensemble de didacticiels git de Atlassian.</span><span class="sxs-lookup"><span data-stu-id="d1233-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="d1233-112">[Gestion de version dans Visual Studio code](https://code.visualstudio.com/docs/editor/versioncontrol): Guide d’utilisation de Visual Studio code en tant qu’interface utilisateur graphique pour git.</span><span class="sxs-lookup"><span data-stu-id="d1233-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="d1233-113">[GitHub Learning Lab](https://lab.github.com/): un ensemble de formations en ligne pour l’utilisation de git, GitHub et des technologies associées.</span><span class="sxs-lookup"><span data-stu-id="d1233-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="d1233-114">[Visualisation de git](https://git-school.github.io/visualizing-git/): outil interactif permettant de visualiser la façon dont les commandes git modifient l’état d’un référentiel.</span><span class="sxs-lookup"><span data-stu-id="d1233-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="d1233-115">[Gestion de version avec git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): un didacticiel git orienté vers l’informatique scientifique.</span><span class="sxs-lookup"><span data-stu-id="d1233-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="d1233-116">[Découvrez git Branching](https://learngitbranching.js.org/): un ensemble interactif de puzzles et de relocalisation pour vous aider à découvrir de nouvelles fonctionnalités git.</span><span class="sxs-lookup"><span data-stu-id="d1233-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="d1233-117">Qu’est-ce qu’une requête de tirage ?</span><span class="sxs-lookup"><span data-stu-id="d1233-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="d1233-118">En ayant dit ce qui précède, il est utile de prendre quelques instants pour dire ce qu' **est**une requête de tirage.</span><span class="sxs-lookup"><span data-stu-id="d1233-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="d1233-119">Lorsque vous utilisez git, toutes les modifications sont représentées en tant que _validations_ qui décrivent comment ces modifications sont liées à l’état du dépôt avant ces modifications.</span><span class="sxs-lookup"><span data-stu-id="d1233-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="d1233-120">Nous allons souvent dessiner des diagrammes dans lesquels les validations sont dessinées sous forme de cercles avec des flèches issues des validations précédentes.</span><span class="sxs-lookup"><span data-stu-id="d1233-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="d1233-121">Supposons que vous avez commencé une contribution dans une _branche_ appelée `feature`.</span><span class="sxs-lookup"><span data-stu-id="d1233-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="d1233-122">Votre fourche de **Microsoft/Quantum** peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="d1233-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![](~/media/git-workflow-step0.png)

<span data-ttu-id="d1233-123">Si vous apportez vos modifications dans votre référentiel local, vous pouvez _extraire_ les modifications d’un autre référentiel dans le vôtre pour prendre en forme les modifications qui se sont produites en amont.</span><span class="sxs-lookup"><span data-stu-id="d1233-123">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![](~/media/git-workflow-step1.png)

<span data-ttu-id="d1233-124">Les requêtes de tirage fonctionnent de la même façon, mais dans l’ordre inverse : lorsque vous ouvrez une requête de tirage, vous demandez au référentiel en amont d’extraire votre contribution.</span><span class="sxs-lookup"><span data-stu-id="d1233-124">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![](~/media/git-workflow-step2.png)

<span data-ttu-id="d1233-125">Lorsque vous ouvrez une demande de tirage (pull request) dans l’un de nos référentiels, GitHub offre une opportunité aux autres membres de la communauté d’afficher un résumé de vos modifications, de les commenter et d’apporter des suggestions sur la façon d’améliorer la contribution.</span><span class="sxs-lookup"><span data-stu-id="d1233-125">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![](~/media/pull-request-header.png)

<span data-ttu-id="d1233-126">L’utilisation de ce processus nous aide à utiliser la fonctionnalité GitHub pour améliorer les contributions et maintenir un produit de haute qualité pour la communauté de programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="d1233-126">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="d1233-127">Comment effectuer une requête de tirage (pull request)</span><span class="sxs-lookup"><span data-stu-id="d1233-127">How to Make a Pull Request</span></span> ##

<span data-ttu-id="d1233-128">Il existe deux méthodes principales pour effectuer une demande de tirage (pull request).</span><span class="sxs-lookup"><span data-stu-id="d1233-128">There are two main ways to make a pull request.</span></span>
<span data-ttu-id="d1233-129">Pour les petites modifications qui n’affectent qu’un seul fichier, l’interface Web GitHub peut être utilisée pour effectuer une requête de tirage entièrement en ligne.</span><span class="sxs-lookup"><span data-stu-id="d1233-129">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span>
<span data-ttu-id="d1233-130">Pour les contributions plus complexes, il est souvent plus facile d’utiliser votre ordinateur local pour préparer une demande de tirage.</span><span class="sxs-lookup"><span data-stu-id="d1233-130">For more complicated contributions, it's most often easier to use your local computer to prepare for a pull request first.</span></span>

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a><span data-ttu-id="d1233-131">Prochaines étapes</span><span class="sxs-lookup"><span data-stu-id="d1233-131">Next steps</span></span> ##

<span data-ttu-id="d1233-132">Félicitations pour l’utilisation de Git pour aider la communauté du kit de développement quantique !</span><span class="sxs-lookup"><span data-stu-id="d1233-132">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="d1233-133">Pour en savoir plus sur la façon de contribuer au code, poursuivez avec le guide suivant.</span><span class="sxs-lookup"><span data-stu-id="d1233-133">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d1233-134">Apprenez à contribuer au code</span><span class="sxs-lookup"><span data-stu-id="d1233-134">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
