---
title: Que peuvent faire les ordinateurs quantiques ?
description: Découvrez l’impact de l’informatique quantique, des nouveaux algorithmes quantiques aux algorithmes inspirés des technologies quantiques fonctionnant sur des ordinateurs classiques.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: 9d8ba90a504f298f9465ebf564c43625a4d43168
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2020
ms.locfileid: "73529947"
---
# <a name="what-can-a-quantum-computer-do"></a>Que sont capables de faire les ordinateurs quantiques ?

Qu’est-il possible de faire avec un ordinateur quantique qui ne peut être fait avec un ordinateur classique ?

Un ordinateur quantique pourrait résoudre en quelques jours, heures voire minutes certains des problèmes les plus épineux qui soient, dont la résolution prendrait des milliards d’années avec des ordinateurs classiques.

L’informatique quantique permettra aux chercheurs de développer de nouveaux catalyseurs et matériaux, d’améliorer des médicaments, d’accélérer les progrès de l’intelligence artificielle et de répondre à des questions fondamentales sur les origines de notre univers.

## <a name="quantum-simulation"></a>Simulation quantique

L’utilisation de programmes quantiques pour modéliser des systèmes quantiques représente un énorme potentiel pour découvrir des insights susceptibles de mener à des innovations dans de nombreux secteurs. La photosynthèse, les supraconducteurs et les molécules complexes sont des exemples de systèmes quantiques qu’il est possible de simuler à l’aide de programmes quantiques.

La simulation de systèmes microscopiques se comportant conformément aux lois de la mécanique quantique est coûteuse en matière de calcul. Il faut prendre en compte tous les états possibles pouvant être en superposition, alors que le nombre d’états augmente de manière exponentielle avec la taille du système. Dans un ordinateur quantique, il n’est pas nécessaire de modéliser tous les états du système. Au lieu de cela, nous incorporons l’état quantique du système que nous voulons simuler dans les qubits de l’ordinateur lui-même, et exécutons la simulation avec un ensemble spécifique de portes quantiques. Autrement dit, nous utilisons un ordinateur quantique pour simuler un système quantique.

Les molécules chimiques étant des systèmes quantiques, il est possible de les analyser de cette manière. L’un de ces produits chimiques est l’enzyme _nitrogénase_ qui, avec une meilleure compréhension de ses propriétés, pourrait réduire la consommation d’énergie et les émissions de gaz à effet de serre des engrais.

## <a name="cryptography"></a>Chiffrement

Le chiffrement est peut-être devenu l’application la plus célèbre des ordinateurs quantiques, quand, en 1994, Peter Shori a montré qu’un ordinateur quantique scalable pouvait décrypter toutes les techniques de chiffrement connues de l’époque.  Le chiffrement classique repose sur l’insolubilité des opérations sur de grands nombres, comme la factorisation de grands nombres en deux nombres premiers.

L’informatique quantique rend ces opérations théoriquement solubles (par le biais de l’algorithme de Shor). Si l’implémentation de cet algorithme n’est pas physiquement possible en raison de l’échelle actuelle du matériel quantique, il a permis de développer des algorithmes quantiques robustes pour une sécurité durable des données, parmi lesquels de nouveaux algorithmes quantiques pour le chiffrement et la distribution de clés de chiffrement.

Chez Microsoft, nous avons la meilleure équipe au monde dans le domaine du chiffrement post-quantique et de la sécurité qui développe des algorithmes résistants aux ordinateurs quantiques.

## <a name="optimization"></a>Optimization

L’optimisation est la tâche qui consiste à effectuer une recherche poussée dans un espace dimensionnel élevé d’une solution qui réduit au minimum une fonction coût donnée.   Sur un ordinateur quantique, nous pouvons accélérer les algorithmes d’optimisation, ce qui permet de trouver des solutions qui, sans cela, n’étaient pas possibles. Les applications s’étendent du domaine des transports et de la logistique à celui de la santé, en passant par le diagnostic et la science des matériaux. L’impact sur l’efficacité de ces secteurs peut être colossal.

L’optimisation avec l’informatique quantique nous permet d’innover dans le domaine des transports et de la logistique d’une façon qui n’est pas possible avec les systèmes classiques d’aujourd’hui.

En effet, l’optimisation des flux de trafic peut permettre de réduire les embouteillages.  En plus de mieux planifier les itinéraires, il devient possible de mieux affecter les portes d’embarquement dans les aéroports, de mieux distribuer les colis, de mieux planifier les tâches, etc. Les innovations dans le domaine de la science des matériaux vont générer de nouvelles formes d’énergie, des batteries avec une capacité plus grande, des matériaux plus légers et plus résistants.

## <a name="machine-learning"></a>Apprentissage automatique

En informatique classique, un grand nombre de calculs numériques consistent principalement à résoudre des systèmes linéaires d’équations. C’est particulièrement vrai dans le domaine de l’apprentissage automatique, où ces calculs visent essentiellement à calculer l’inverse de matrices énormes.

Fort heureusement, il existe un algorithme quantique permettant de résoudre approximativement le système de façon exponentiellement plus rapide qu’un ordinateur classique. L’algorithme ouvre la voie à des accélérations spectaculaires dans le traitement de chaque problème nécessitant la résolution de systèmes linéaires d’équations.

Les solutions aux problèmes dans ces domaines permettront de mieux gérer la crise de l’énergie, le changement climatique, la pénurie alimentaire et le diagnostic médical personnel et précis.

## <a name="quantum-inspired-computing"></a>Informatique inspirée de la physique quantique

Les algorithmes inspirés de la physique quantique sont implémentés à l’aide de logiciels classiques, mais utilisent des principes quantiques pour accroître la vitesse et la précision.

Des algorithmes inspirés de la physique quantique sont appliqués à la recherche médicale. C’est le cas, par exemple, pour améliorer la précision de l’imagerie par résonance magnétique (IRM). Une informatique inspirée de la physique quantique est utilisée pour optimiser la configuration des appareils IRM afin d’identifier des maladies spécifiques.

## <a name="next-steps"></a>Étapes suivantes

* [Pourquoi apprendre l’informatique quantique ?](xref:microsoft.quantum.overview.why)
* [Prise en main du Quantum Development Kit de Microsoft](xref:microsoft.quantum.welcome)
