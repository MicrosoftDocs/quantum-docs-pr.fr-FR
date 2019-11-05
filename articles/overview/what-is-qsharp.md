---
title: Qu’est-ce que Q# ?
description: Découvrez Q#, un langage de programmation créé par Microsoft afin de développer des applications pour ordinateurs quantiques
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04228ff62092a15c529297bd56b9ee48399f4a5
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443951"
---
# <a name="what-is-q"></a>Qu’est-ce que Q# ?

Q# est un langage de programmation offrant des fonctionnalités spécifiques de l’informatique quantique. Q# fournit aux programmeurs quantiques une infrastructure leur permettant de se concentrer sur les algorithmes sans se soucier de détails techniques tels que l’optimisation de séquence de portes ou l’implémentation physique d’un ordinateur quantique.

Le langage de programmation Q# offre un ensemble intuitif de types, d’opérations et d’expressions logiques pour développer des algorithmes sans se soucier de la logique interne de l’ordinateur quantique.

## <a name="code-algorithms"></a>Codez des algorithmes

Aux débuts de l’informatique quantique, les algorithmes étaient perçus comme des schémas de la même façon que les schémas électriques en informatique classique.  Si le modèle de circuit a été très utile pendant de nombreuses années pour la recherche en informatique quantique, chez Microsoft, nous pensons que les développeurs peuvent aller au-delà des circuits quantiques pour développer des algorithmes et applications quantiques en Q#. Le langage Q# a été conçu pour tirer parti de ce que nous avons appris au fil de décennies de développement de logiciels classiques, et doter les développeurs quantiques d’un langage de haut niveau spécifiquement conçu pour l’informatique quantique.


## <a name="how-does-q-work"></a>Comment fonctionne Q# ?

L’une des pierres angulaires du langage Q# est le type `Qubit`, qui ne peut pas être copié ou faire l’objet d’un accès direct, à l’instar d’un véritable qubit. Au lieu de cela, nous pouvons le mesurer et stocker le résultat de la mesure dans une variable `Result`, un type Q# pouvant prendre deux valeurs possibles : `Zero` et `One`. Des constructions telles que celle-ci garantissent que les algorithmes respectent toujours les lois de la physique quantique et peuvent fonctionner correctement sur des ordinateurs quantiques ou des simulateurs.

Q# inclut également des fonctionnalités logiques classiques telles que des conditions ou des boucles, agrémentées de quelques subtilités destinées à assurer le respect de toutes les règles quantiques. Par exemple, les opérations quantiques doivent être réversibles. Cela impose certaines contraintes quant à la manière dont les boucles sont exécutées.

Les programmes Q# sont souvent associés à un programme hôte écrit en C# ou Python, qui peut faciliter l’organisation de code classique et quantique. En plus de prendre en charge les langages .NET tels que C# et Python, le QDK prend en charge Jupyter Notebook avec le noyau IQ# Jupyter.

## <a name="use-q-to-learn-quantum-computing"></a>Utilisez Q# pour apprendre l’informatique quantique

Jusqu’à ce jour, pour apprendre l’informatique quantique, vous deviez apprendre le modèle de circuit afin de comprendre les algorithmes comme des séquences ordonnées de portes et de mesures quantiques. Avec Q#, vous pouvez emprunter une autre voie : apprendre l’informatique quantique en écrivant des programmes quantiques.

## <a name="use-q-to-design-quantum-algorithms"></a>Utiliser Q# pour concevoir des algorithmes quantiques

Q# fournit un nombre croissant de bibliothèques et de types définis par des utilisateurs, qui vous aident à implémenter des outils et à créer des algorithmes quantiques avancés. Par exemple, vous devez intriquer deux qubits ? Au lieu d’appliquer individuellement les portes nécessaires intriquer les qubits, vous pouvez utiliser l’opération intégrée `PrepareEntangledState([q1], [q2])`.

## <a name="use-q-to-estimate-quantum-resources"></a>Utiliser Q# pour estimer des ressources quantiques

Vous pouvez simuler l’exécution de votre programme Q# à l’aide du simulateur quantique d’état complet fourni avec le Quantum Development Kit (QDK).  Le QDK fournit également des estimateurs de ressources qui vous donnent des insights sur les performances des programmes Q# trop colossaux pour être exécutés sur un simulateur.  Ces estimateurs s’avèrent très utiles pour les concepteurs d’algorithmes, car ils permettent d’ajuster les programmes afin d’utiliser moins de ressources (par exemple, moins de qubits s’exécutent pour un nombre d’opérations inférieur) et d’exécuter les programmes sur du matériel quantique antérieur à plus petite échelle.   

## <a name="use-q-to-validate-hardware-performance"></a>Utiliser Q# pour valider des performances matérielles

Ce qui est remarquable avec Q#, c’est qu’un programme peut être écrit une seule fois mais exécuté sur des simulateurs quantiques à des fins de débogage et exécuté sur le matériel de plusieurs ordinateurs quantiques.  Les programmes de benchmark écrits en Q# peuvent être exécutés pour valider les performances matérielles et comparer les résultats à mesure que les ordinateurs quantiques évoluent et que de nouveaux ordinateurs quantiques deviennent disponibles.  

## <a name="next-steps"></a>Étapes suivantes

* [Comment apprendre l'informatique quantique ?](xref:microsoft.quantum.overview.learn)
* [Prise en main du Quantum Development Kit de Microsoft](xref:microsoft.quantum.welcome)
