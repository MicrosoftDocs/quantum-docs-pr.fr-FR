---
title: Présentation de Q# et du QDK
description: Découvrez Q#, langage de programmation créé par Microsoft afin de développer des applications pour ordinateurs quantiques et composant clé du Kit de développement Microsoft Quantum
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906999"
---
# <a name="what-are-q-and-the-qdk"></a>Présentation de Q# et du QDK

Q# est un langage de programmation avec des fonctionnalités spécifiquement conçues pour être utilisées avec l’informatique quantique.
Composant clé du Kit de développement Microsoft Quantum (QDK), il fournit aux programmeurs quantiques une infrastructure leur permettant de se concentrer sur les algorithmes sans se soucier des détails techniques tels que l’optimisation de séquence de portes ou l’implémentation physique d’un ordinateur quantique.

Le kit QDK comprend un large choix d’outils qui offrent aux développeurs tout ce dont ils ont besoin pour commencer à écrire des programmes quantiques.
En plus du langage Q#, le kit QDK comprend :
* Les *bibliothèques Q#* , qui permettent aux développeurs de se mettre tout de suite au travail et de créer des applications quantiques concrètes
* Diverses *machines cibles* sur lesquelles les programmes Q# peuvent être exécutés. Cela comprend des simulateurs et des estimateurs de ressources pour des programmes quantiques plus grands, ainsi qu’un simulateur quantique complet qui se comporte comme un ordinateur quantique sans parasite. Ce dernier est très utile pour repenser des idées, déboguer des programmes et apprendre la physique quantique, mais seulement efficace pour les programmes avec relativement peu de qubits. Nous sommes vraiment impatients d’avoir à disposition du matériel d’informatique quantique comme machines cibles.
* Des *outils* pour un fonctionnement aussi fluide que possible avec Q#, comme des extensions pour Visual Studio et VS Code, et des packages à utiliser avec Python et Jupyter Notebooks.
* Une *documentation sur les API* pour coupler Q# avec les langages d’hôte classiques comme Python et C#

Les applications développées avec le Kit de développement Microsoft Quantum comprennent deux composantes :
1. Un ou plusieurs algorithmes quantiques, implémenté avec le langage de programmation quantique Q# et appelé par le programme d’hôte classique. Il s’agit des 
    - opérations Q# : sous-routines contenant des opérations quantiques et des 
    - fonctions Q# : sous-routines classiques utilisées dans l’algorithme quantique.
2. Un programme classique, implémenté dans un langage de programmation classique comme Python ou C#, qui sert de point d’entrée principal et appelle des opérations Q# quand il veut exécuter un algorithme quantique.

## <a name="write-quantum-programs-not-quantum-circuits"></a>Écrire des programmes quantiques, pas des circuits quantiques

Aux débuts de l’informatique quantique, les algorithmes étaient perçus comme des schémas de la même façon que les schémas électriques en informatique classique.
Si le modèle de circuit a été utile pendant de nombreuses années pour la recherche en informatique quantique, chez Microsoft, nous pensons que les développeurs peuvent aller au-delà des circuits quantiques pour développer des algorithmes et applications quantiques en Q#.
Le langage Q# a été conçu pour tirer parti de ce que nous avons appris au fil de décennies de développement de logiciels classiques, et pour doter les développeurs quantiques d’un langage de haut niveau spécifiquement conçu pour l’informatique quantique.

## <a name="how-does-q-work"></a>Comment fonctionne Q# ?

Le langage de programmation Q# offre un ensemble intuitif de types, d’opérations et d’expressions logiques pour développer des algorithmes sans se soucier de la logique interne de l’ordinateur quantique.

L’une des pierres angulaires du langage Q# est le type `Qubit`, qui ne peut pas être copié ou faire l’objet d’un accès direct, à l’instar d’un véritable qubit.
Au lieu de cela, nous pouvons le mesurer et stocker le résultat de la mesure dans une variable `Result`, un type Q# pouvant prendre deux valeurs possibles : `Zero` et `One`.
Des constructions telles que celle-ci garantissent que les algorithmes respectent toujours les lois de la physique quantique et peuvent fonctionner correctement sur des ordinateurs quantiques ou des simulateurs.

Q# inclut également des fonctionnalités logiques classiques telles que des conditions et des boucles, agrémentées de quelques subtilités destinées à assurer le respect de toutes les règles quantiques.
Par exemple, limiter la façon dont les boucles sont exécutées pour s’assurer que les opérations quantiques ne sont pas appelées dans les fonctions qui peuvent uniquement contenir des sous-routines classiques déterministes.

Les programmes Q# sont souvent associés à un programme hôte écrit en C# ou Python, qui peut faciliter l’organisation de code classique et quantique.
En plus de prendre en charge des langages tels que C# et Python, le QDK prend en charge Jupyter Notebook avec le noyau IQ# Jupyter.

## <a name="what-can-i-use-q-for"></a>Pourquoi utiliser Q# ?

### <a name="use-q-to-learn-quantum-computing"></a>Utilisez Q# pour apprendre l’informatique quantique

Jusqu’à ce jour, pour apprendre l’informatique quantique, vous deviez apprendre le modèle de circuit afin de comprendre les algorithmes comme des séquences ordonnées de portes et de mesures quantiques. Avec Q#, vous pouvez emprunter une autre voie : apprendre l’informatique quantique en écrivant des programmes quantiques.

### <a name="use-q-to-design-quantum-algorithms"></a>Utiliser Q# pour concevoir des algorithmes quantiques

Q# fournit un nombre croissant de bibliothèques et de types définis par des utilisateurs, qui vous aident à implémenter des outils et à créer des algorithmes quantiques avancés. Par exemple, vous devez intriquer deux qubits ? Au lieu d’appliquer individuellement les portes nécessaires intriquer les qubits, vous pouvez utiliser l’opération intégrée `PrepareEntangledState([q1], [q2])`.

### <a name="use-q-to-estimate-quantum-resources"></a>Utiliser Q# pour estimer des ressources quantiques

Vous pouvez simuler l’exécution de votre programme Q# à l’aide du simulateur quantique d’état complet fourni avec le Quantum Development Kit (QDK).  Le QDK fournit également des estimateurs de ressources qui vous donnent des insights sur les performances des programmes Q# trop colossaux pour être exécutés sur un simulateur.  Ces estimateurs s’avèrent très utiles pour les concepteurs d’algorithmes, car ils permettent d’ajuster les programmes afin d’utiliser moins de ressources (par exemple, moins de qubits s’exécutent pour un nombre d’opérations inférieur) et d’exécuter les programmes sur du matériel quantique antérieur à plus petite échelle.

### <a name="use-q-to-validate-hardware-performance"></a>Utiliser Q# pour valider des performances matérielles

Ce qui est remarquable avec Q#, c’est qu’un programme peut être écrit une seule fois mais exécuté sur des simulateurs quantiques à des fins de débogage et exécuté sur le matériel de différents ordinateurs quantiques.  Les programmes de benchmark écrits en Q# peuvent être exécutés pour valider les performances matérielles et comparer les résultats à mesure que les ordinateurs quantiques évoluent et que de nouveaux ordinateurs quantiques deviennent disponibles.  

## <a name="next-steps"></a>Étapes suivantes

* [Comment m’informer sur l’informatique quantique ?](xref:microsoft.quantum.overview.learn)
* [Prise en main du Quantum Development Kit de Microsoft](xref:microsoft.quantum.welcome)
