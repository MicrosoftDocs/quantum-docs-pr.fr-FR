---
title: Présentation de l’informatique quantique
description: Découvrez ce qu’est l’informatique quantique, ce que les ordinateurs peuvent faire et comment apprendre l’informatique quantique.
author: bradben
ms.author: v-benbra
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3374e9fae07cc38761e404be7819e7cf699ce2b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834514"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>Introduction à l’informatique quantique et au kit de développement Quantum

Le kit de développement Microsoft Quantum (QDK, Quantum Development kit) est un ensemble d’outils open source conçus pour aider les développeurs à se familiariser avec les algorithmes quantiques et à écrire des programmes quantiques. L’informatique quantique promet de résoudre certains des plus grands défis auxquels notre planète est confrontée dans les domaines de l’environnement, de l’agriculture, de la santé, de l’énergie, du climat et de la science des matériaux, sans parler des autres dont nous n’avons pas encore connaissance.  

Même les ordinateurs les plus puissants que nous utilisons aujourd’hui ne sont pas capables de résoudre tous ces problèmes. La technologie quantique commence à peine à avoir des répercussions dans le monde de l’informatique, mais elle pourrait à l’avenir avoir une portée considérable et changer notre façon d’appréhender l’informatique.

## <a name="what-is-quantum-computing"></a>Qu’est-ce que l’informatique quantique ?

Dans son usage actuel, le mot « quantique » désigne la plus petite unité discrète possible d’une propriété physique, qui fait généralement référence à des propriétés de particules atomiques ou subatomiques. Les ordinateurs quantiques utilisent des particules quantiques réelles, des atomes artificiels ou des propriétés collectives de particules quantiques comme unités de traitement. Ce sont des appareils volumineux, complexes et onéreux.

En exploitant le comportement caractéristique de la physique quantique et en l’appliquant à l’informatique, les ordinateurs quantiques introduisent de nouveaux concepts par rapport aux méthodes de programmation classiques, en reprenant certains comportements de la physique quantique comme la superposition, l’intrication et l’interférence quantique.

## <a name="what-can-a-quantum-computer-do"></a>Que sont capables de faire les ordinateurs quantiques ?

Un ordinateur quantique n’est pas un superordinateur capable de tout faire plus vite, mais il excelle dans plusieurs domaines.

- [Simulation quantique](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Cryptographie](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [action](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [Optimisation](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [Machine Learning](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Simulation quantique

Du fait que les ordinateurs quantiques utilisent des phénomènes quantiques dans le calcul, ils sont particulièrement bien adaptés pour la modélisation d’autres systèmes quantiques. La photosynthèse, la supraconductivité et les formes moléculaires complexes sont des exemples de mécanismes quantiques que les programmes quantiques sont capables de simuler.

## <a name="cryptography-and-shors-algorithm"></a>Le chiffrement et l’algorithme de Shor

En 1994, Peter Shor a montré qu’un ordinateur quantique scalable pouvait réussir à casser les techniques de chiffrement courantes actuelles, telles que l’algorithme RSA. Le chiffrement classique est basé sur l’impossibilité de résoudre des problèmes tels que la factorisation des entiers ou les logarithmes discrets, or la plupart de ces problèmes pourraient être résolus plus facilement à l’aide d’ordinateurs quantiques.

## <a name="search-and-grovers-algorithm"></a>La recherche et l’algorithme de Grover

En 1996, Lov Grover a développé un algorithme quantique qui a donné un grand coup d’accélérateur dans le traitement des recherches de données non structurées, en réduisant le nombre des étapes de recherche comme aucun algorithme classique ne l’avait fait auparavant.

## <a name="quantum-inspired-computing-and-optimization"></a>Informatique inspirée de la physique quantique et optimisation

Les algorithmes inspirés de la physique quantique utilisent des principes quantiques pour accroître la vitesse et la précision, mais ils sont implémentés sur des ordinateurs classiques. Cette approche permet aux développeurs de profiter de la puissance des nouvelles techniques quantiques dès maintenant, sans avoir à attendre le matériel quantique, qui est encore un secteur émergeant.

L’optimisation est le processus qui consiste à trouver la meilleure solution à un problème, en prenant en compte les contraintes et le résultat souhaité. Divers facteurs tels que le coût, la qualité et le temps de production jouent un rôle essentiel dans les décisions critiques prises par les acteurs des milieux industriels et scientifiques. Les algorithmes d’optimisation inspirés de la physique quantique qui sont exécutés sur les ordinateurs classiques actuels sont capables de trouver des solutions à des problèmes jusque-là insolvables. En plus d’optimiser le flux du trafic pour réduire les points de congestion, il devient possible de mieux affecter les portes d’embarquement dans les aéroports, de mieux distribuer les colis, de mieux planifier les tâches, etc. Les innovations dans le domaine de la science des matériaux vont générer de nouvelles formes d’énergie, des batteries de plus grande capacité, et des matériaux plus légers et plus durables.

> [!NOTE]
> Découvrez-en plus sur les utilisations de l’informatique quantique de Microsoft dans les domaines de la [science des matériaux](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), de la [gestion des risques](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) et de la [médecine](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).

## <a name="quantum-machine-learning"></a>Machine Learning quantique

Le Machine Learning sur les ordinateurs classiques est en train de révolutionner le monde de l’entreprise et de la science. Toutefois, le coût élevé des calculs d’entraînement des modèles entrave le développement et l’élargissement de ce champ d’activité. Le domaine du Machine Learning quantique explore des façons de concevoir et d’implémenter des logiciels quantiques qui permettraient d’exécuter le Machine Learning plus rapidement que les ordinateurs classiques.

Le kit de développement Quantum fournit la [bibliothèque de Machine Learning quantique](xref:microsoft.quantum.machine-learning.concepts.intro), qui vous permet d’effectuer des expériences de Machine Learning hybride quantique/classique. En plus d’inclure des exemples et des tutoriels, la bibliothèque fournit les outils nécessaires pour implémenter un nouvel algorithme hybride quantique/classique, le classifieur quantique centré sur le circuit, pour résoudre les problèmes de classification supervisée.

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a>Q# et le kit de développement Microsoft Quantum (QDK)

Q# est le langage de programmation open source conçu par Microsoft pour le développement et l’exécution d’algorithmes quantiques. Il fait partie du [QDK](https://docs.microsoft.com/quantum/), un kit de développement complet pour Q# que vous pouvez utiliser avec des outils et des langages standard pour développer des applications quantiques exécutables dans divers environnements, y compris le simulateur d’état quantique complet intégré.

Il existe des extensions pour Visual Studio et Visual Studio Code, ainsi que des packages pour Python et Jupyter Notebook.

En plus de la bibliothèque standard, le QDK contient des bibliothèques spécialisées de données numériques, de chimie et de Machine Learning.

La documentation comprend un guide du langage Q#, des tutoriels et des exemples de code pour vous aider à démarrer rapidement. Elle inclut aussi des articles complets qui vous permettront d’approfondir les concepts de l’informatique quantique.  

## <a name="microsoft-quantum-hardware-partners"></a>Partenariats entre Microsoft et des fabricants de matériel quantique

Microsoft travaille en partenariat avec des fabricants de matériel quantique pour permettre aux développeurs d’accéder à du matériel quantique dans le cloud. En exploitant la plateforme [Azure Quantum](https://azure.microsoft.com/services/quantum/) et le langage Q#, les développeurs pourront explorer les algorithmes quantiques et exécuter leurs programmes quantiques sur différents types de matériel quantique.

[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) et [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) utilisent tous deux des processeurs **basés sur des ions piégés**, en utilisant les ions individuels piégés dans un champ électronique, tandis que [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) utilise des circuits supraconducteurs.

## <a name="next-steps"></a>Étapes suivantes

[Concepts fondamentaux de l’informatique quantique](xref:microsoft.quantum.overview.understanding)
[Tutoriels](xref:microsoft.quantum.welcome)