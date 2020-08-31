---
uid: microsoft.quantum.welcome
title: Bien démarrer avec le Quantum Development Kit (QDK)
description: Découvrez comment commencer à programmer des projets quantiques en Q# avec le kit de développement Microsoft Quantum.
author: bradben
ms.author: bradben
ms.date: 5/10/2020
ms.topic: overview
no-loc:
- Q#
- $$v
ms.openlocfilehash: 06198f3b5b806bab49abf9fca38b5d2f15cfb65f
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863752"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Bien démarrer avec le Quantum Development Kit (QDK)

Bienvenue dans le Microsoft Quantum Development kit  

Le kit de développement Quantum (QDK, Quantum development kit) contient tous les outils dont vous aurez besoin pour créer vos propres expérimentations et programmes quantiques avec Q#, langage de programmation conçu spécifiquement pour le développement d’applications quantiques.

Pour démarrer rapidement, commencez par le [guide d’installation du QDK](xref:microsoft.quantum.install).
Ce guide vous montre pas à pas comment installer le kit de développement Quantum sur des machines Windows, Linux ou MacOS afin que vous puissiez ensuite écrire vos propres programmes quantiques.

Si vous ne connaissez pas encore l’informatique quantique, lisez la section [Vue d’ensemble](xref:microsoft.quantum.overview.introduction) pour découvrir ce que les ordinateurs quantiques sont capables de faire et comprendre les concepts de base de l’informatique quantique.

## <a name="get-started-programming"></a>Prise en main de la programmation

Le Quantum Development Kit vous offre de nombreuses façons d’apprendre à développer un programme quantique avec Q#.
Pour débuter avec l’informatique quantique et être prêt à en exploiter toute la puissance, vous pouvez suivre nos tutoriels :

* [Générateur de nombres aléatoires quantique](xref:microsoft.quantum.quickstarts.qrng) : commencez avec une application de style « Hello World Q# » qui fournit une brève introduction des concepts de l’informatique quantique tout en vous permettant de créer et d’exécuter une application quantique en seulement quelques minutes.
* [Explorer l’intrication avec Q#](xref:microsoft.quantum.write-program) : ce tutoriel vous guide pour écrire un programme Q# qui illustre certains des concepts fondamentaux de la programmation quantique.
    Si vous n’êtes pas prêt à commencer à écrire du code, vous pouvez quand même suivre le tutoriel sans installer le QDK afin d’avoir une vue d’ensemble du langage de programmation Q# et des concepts cardinaux de l’informatique quantique.
* [Algorithme de recherche de Grover](xref:microsoft.quantum.quickstarts.search) : consultez cet exemple de programme Q# qui donne une idée de la puissance du langage Q# pour exprimer l’algorithme quantique en effectuant l’abstraction des opérations quantiques de bas niveau.
    Ce tutoriel vous guide dans le développement du programme sous forme d’application Q# dans Visual Studio ou Visual Studio Code.

### <a name="learning-further"></a>En savoir plus
* Les [modules Microsoft Learn sur l’informatique quantique](https://docs.microsoft.com/learn/browse/?term=quantum) vous permettent d’apprendre les concepts fondamentaux à votre rythme et selon votre planning. Notre [premier module](https://docs.microsoft.com/learn/modules/qsharp-create-first-quantum-development-kit/) vous fait découvrir les principes de base de la création de programmes quantiques avec le QDK.
* Si vous souhaitez aller plus loin dans la programmation Q#, consultez les [katas sur l’informatique quantique](https://github.com/Microsoft/QuantumKatas), collection d’exercices de programmation auto-rythmés qui vous initient à l’informatique quantique par le biais d’exercices de programmation en Q#.
    Un grand nombre de ces katas sont également disponibles sous forme de notebooks Q#. 
* Notre [dépôt d’exemples](https://github.com/Microsoft/Quantum) présente plusieurs exemples d’écriture de programmes quantiques à l’aide de Q#. La plupart de ces exemples sont écrits à l’aide de nos [bibliothèques quantiques open source](https://github.com/Microsoft/QuantumLibraries), y compris nos bibliothèques [standard](xref:microsoft.quantum.libraries.standard.intro) et de [chimie](xref:microsoft.quantum.chemistry.concepts.intro) (sur lesquelles nous revenons plus loin).

## <a name="key-concepts-for-quantum-computing"></a>Concepts fondamentaux de l’informatique quantique

Si vous êtes novice en développement quantique, nous savons que cette matière peut sembler un peu décourageante. L’explication de ces concepts fondamentaux vise à vous aider à vous lancer dans le monde du quantique et à comprendre en quoi l’informatique quantique diffère de l’informatique classique.

* [Fonctionnement de l’informatique quantique](xref:microsoft.quantum.overview.understanding)
* [Ordinateurs quantiques et simulateurs quantiques](xref:microsoft.quantum.overview.simulators)
* [Présentation du langage de programmation Q# et du QDK](xref:microsoft.quantum.overview.q-sharp)
* [Algèbre linéaire pour l’informatique quantique](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a>Documentation relative au Quantum Development Kit

La documentation actuelle contient les sujets supplémentaires suivants.

### <a name="no-locq-developer-guides"></a>Guides du développeur Q#

* [Le Guide de l’utilisateur Q#](xref:microsoft.quantum.guide) détaille les concepts de base utilisés pour la création de programmes quantiques en Q#.
* L’article [Simulateurs quantiques et applications hôtes](xref:microsoft.quantum.machines) décrit l’exécution des algorithmes quantiques, les machines quantiques disponibles et l’écriture d’un pilote non Q# pour le programme quantique.

### <a name="no-locq-libraries"></a>Bibliothèques Q#

* L’article [Bibliothèques standard Q#](xref:microsoft.quantum.libraries.standard.intro) décrit les opérations et les fonctions qui prennent en charge à la fois la spécification du contrôle de langage classique et les algorithmes quantiques Q#. 
    Les sujets abordés incluent le flux de contrôle, les structures de données, la correction des erreurs, le test et le débogage. 
* L’article [Bibliothèque de chimie Q#](xref:microsoft.quantum.chemistry.concepts.intro) décrit les opérations et les fonctions qui prennent en charge la simulation de chimie quantique, application critique d’informatique quantique. Les sujets abordés incluent la simulation de la dynamique hamiltonienne et l’estimation des phases quantiques, entre autres.
* L’article [Bibliothèque de valeurs numériques Q#](xref:microsoft.quantum.numerics.intro) décrit les opérations et les fonctions qui prennent en charge l’expression des fonctions arithmétiques complexes en termes d’opérations natives des machines cibles.
* L’article [Informations de référence sur les bibliothèques Q#](xref:microsoft.quantum.standardlibsintro) contient des informations de référence sur les entités de bibliothèque par espace de noms.

### <a name="general-quantum-computing"></a>Informatique quantique générale

* L’article [Concepts de l’informatique quantique](xref:microsoft.quantum.concepts.intro) incluent des sujets tels que la pertinence de l’algèbre linéaire pour l’informatique quantique, la nature et l’utilisation d’un qubit, la lecture d’un circuit quantique et bien plus encore.
* L’article [Glossaire de l’informatique quantique](xref:microsoft.quantum.glossary) est un glossaire de quelques termes cruciaux spécifiques à l’informatique et au développement de programmes quantiques.
    Si vous débutez dans ce domaine, n’hésitez pas à vous y référer au fil de la lecture de notre documentation.
* L’article [Lectures supplémentaires](xref:microsoft.quantum.more-information) contient une sélection de références couvrant en profondeur les sujets relatifs à l’informatique quantique.

### <a name="additional-info"></a>Informations supplémentaires

* [Notes de publication de Microsoft Quantum Development Kit](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-no-locq-open-source-community"></a>Faire partie de la communauté open source Q#

Le Quantum Development Kit est un kit de développement open source qui permet aux développeurs de rendre l’informatique quantique plus accessible à tous afin que nous puissions relever certains des défis les plus pressants au monde.  Les institutions académiques qui nécessitent des logiciels open source pourront déployer Q# pour mettre en œuvre l’apprentissage de l’informatique quantique et le développement de projets quantiques. Le fait que le kit de développement soit open source permet également aux développeurs et aux experts du domaine de contribuer aux améliorations et aux idées par le biais de leur code.

Vos commentaires, participations et contributions au Quantum Development Kit sont importants.  Pour découvrir les sources du Quantum Development Kit, soumettre des commentaires et savoir comment participer aux décisions et contribuer à cette plateforme de développement quantique en pleine croissance, consultez [Contribution au Quantum Development Kit](xref:microsoft.quantum.contributing).

Si vous souhaitez obtenir des informations plus générales sur l’initiative prise par Microsoft dans le domaine de l’informatique quantique, consultez [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
