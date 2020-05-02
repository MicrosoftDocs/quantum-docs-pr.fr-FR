---
title: Ouverture des requêtes de tirage
description: Découvrez comment envoyer une requête de tirage GitHub quand vous êtes prêt à contribuer au code ou à la documentation sur le Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: 82af3b5123588cc06882f746ffcb0402ad3f0f2e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82686850"
---
# <a name="opening-pull-requests"></a>Ouverture des demandes de tirage (pull requests) #

Toute la documentation du kit de développement Quantum est gérée à l’aide du système de contrôle de version git via l’utilisation de plusieurs dépôts hébergés sur GitHub.
L’utilisation conjointe de git et de GitHub facilite la collaboration sur le kit de développement quantique.
En particulier, tous les référentiels git peuvent être clonés ou dupliqués pour créer une copie totalement indépendante de ce référentiel.
Cela vous permet de travailler sur votre contribution avec les outils et à un rythme que vous préférez.

Lorsque vous êtes prêt, vous pouvez nous envoyer une demande pour inclure votre contribution dans nos dépôts, à l’aide de la fonctionnalité de _demande de tirage (pull Request_ ) de github.
La page de chaque demande de tirage comprend les détails de toutes les modifications qui apportent votre contribution, une liste de commentaires sur votre contribution et un ensemble d’outils de révision que les autres membres de la Communauté peuvent utiliser pour fournir des commentaires et des conseils.

> [!NOTE]
> Bien qu’un didacticiel complet sur git dépasse le cadre de ce guide, nous pouvons suggérer les liens suivants pour obtenir plus de ressources sur la formation git :
>
> - [Découvrez git](https://www.atlassian.com/git): un ensemble de didacticiels git de Atlassian.
> - [Gestion de version dans Visual Studio code](https://code.visualstudio.com/docs/editor/versioncontrol): Guide d’utilisation de Visual Studio code en tant qu’interface utilisateur graphique pour git.
> - [GitHub Learning Lab](https://lab.github.com/): un ensemble de formations en ligne pour l’utilisation de git, GitHub et des technologies associées.
> - [Visualisation de git](https://git-school.github.io/visualizing-git/): outil interactif permettant de visualiser la façon dont les commandes git modifient l’état d’un référentiel.
> - [Gestion de version avec git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): un didacticiel git orienté vers l’informatique scientifique.
> - [Découvrez git Branching](https://learngitbranching.js.org/): un ensemble interactif de puzzles et de relocalisation pour vous aider à découvrir de nouvelles fonctionnalités git.

## <a name="what-is-a-pull-request"></a>Qu’est-ce qu’une requête de tirage ? ##

En ayant dit ce qui précède, il est utile de prendre quelques instants pour dire ce qu' **est**une requête de tirage.
Lorsque vous utilisez git, toutes les modifications sont représentées en tant que _validations_ qui décrivent comment ces modifications sont liées à l’état du dépôt avant ces modifications.
Nous allons souvent dessiner des diagrammes dans lesquels les validations sont dessinées sous forme de cercles avec des flèches issues des validations précédentes.

Supposons que vous avez commencé une contribution _branch_ dans une `feature`branche appelée.
Votre fourche de **Microsoft/Quantum** peut se présenter comme suit :

![Une branche de travail dans GitHub](~/media/git-workflow-step0.png)

Si vous apportez vos modifications dans votre référentiel local, vous pouvez _extraire_ les modifications d’un autre référentiel dans le vôtre pour prendre en forme les modifications qui se sont produites en amont.

![Extraction et fusion des modifications à partir d’un référentiel en amont](~/media/git-workflow-step1.png)

Les requêtes de tirage fonctionnent de la même façon, mais dans l’ordre inverse : lorsque vous ouvrez une requête de tirage, vous demandez au référentiel en amont d’extraire votre contribution.

![Demande d’extraction de vos modifications dans le référentiel d’origine](~/media/git-workflow-step2.png)

Lorsque vous ouvrez une demande de tirage (pull request) dans l’un de nos référentiels, GitHub offre une opportunité aux autres membres de la communauté d’afficher un résumé de vos modifications, de les commenter et d’apporter des suggestions sur la façon d’améliorer la contribution.

![Capture d’écran d’une requête de tirage dans GitHub](~/media/pull-request-header.png)

L’utilisation de ce processus nous aide à utiliser la fonctionnalité GitHub pour améliorer les contributions et maintenir un produit de haute qualité pour la communauté de programmation quantique.

## <a name="how-to-make-a-pull-request"></a>Comment effectuer une requête de tirage (pull request) ##

Il existe deux méthodes principales pour effectuer une demande de tirage (pull request).  
Pour les petites modifications qui n’affectent qu’un seul fichier, l’interface Web GitHub peut être utilisée pour effectuer une requête de tirage entièrement en ligne. Accédez simplement au fichier que vous souhaitez modifier et utilisez l’icône de modification.  
Pour les contributions plus compliquées, il est souvent plus facile de cloner le référentiel sur votre ordinateur local pour préparer une requête de tirage en premier.

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

## <a name="next-steps"></a>Étapes suivantes ##

Félicitations pour l’utilisation de Git pour aider la communauté du kit de développement quantique !
Pour en savoir plus sur la façon de contribuer au code, poursuivez avec le guide suivant.

> [!div class="nextstepaction"]
> [Apprenez à contribuer au code](xref:microsoft.quantum.contributing.code)
