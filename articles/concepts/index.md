---
title: 'Informatique quantique : histoire et contexte'
description: Découvrez l’histoire de l’informatique quantique, son contexte pour comprendre son fonctionnement et le Microsoft Quantum Development Kit.
author: QuantumWriter
ms.author: nawiebe
uid: microsoft.quantum.concepts.intro
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fb1df9e3460c18d0cdc0ff430fa236192b3aa2fa
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442299"
---
# <a name="quantum-computing-history-and-background"></a>Informatique quantique : histoire et contexte

De nombreuses nouvelles technologies informatiques sont apparues au cours des dernières années, et l’informatique quantique est sans doute celle qui nécessite le plus grand changement de paradigme de la part des développeurs.  Les ordinateurs quantiques ont été proposés dans les années 1980 par [Richard Feynman](https://en.wikipedia.org/wiki/Richard_Feynman) et [Yuri Manin](https://en.wikipedia.org/wiki/Yuri_Manin).  L’intuition derrière l’informatique quantique est née de ce qui était souvent considéré comme l’un des plus grands embarras de la physique : des progrès scientifiques remarquables face à une incapacité à modéliser même des systèmes simples. En effet, la mécanique quantique a été développée entre 1900 et 1925 et demeure la pierre angulaire sur laquelle reposent la chimie, la physique de la matière condensée et les technologies allant des puces d’ordinateur à l’éclairage LED.  Pourtant, malgré ces succès, même certains des systèmes les plus simples semblaient être au-delà de la capacité humaine à modéliser avec la mécanisme quantique.  En effet, simuler des systèmes de quelques dizaines de particules en interaction nécessite une puissance de calcul supérieure à celle qu’un ordinateur conventionnel peut fournir sur des milliers d’années !

Il existe de nombreuses façons de comprendre pourquoi la mécanique quantique est difficile à simuler.  Le plus simple est peut-être de voir que la théorie quantique peut être interprétée comme signifiant que la matière, au niveau quantique, se trouve simultanément dans une multitude de configurations différentes possibles (appelées *états*) en même temps.  Contrairement à la théorie classique des probabilités, ces nombreuses configurations de l’état quantique, qui peuvent potentiellement être observées, peuvent interférer les unes avec les autres comme des vagues dans une baïne.  Cette interférence empêche l’utilisation de l’échantillonnage statistique pour obtenir les configurations d’état quantique.  Au lieu de cela, nous devons suivre *toutes les configurations possibles* d’un système quantique si nous voulons comprendre l’évolution quantique.  

Prenons l’exemple d’un système d’électrons dans lequel les électrons peuvent être, disons, dans n’importe laquelle de $40$ positions.  Les électrons peuvent donc être dans n’importe laquelle des $2^{40}$ configurations (puisque chaque position peut avoir ou non un électron). Pour stocker l’état quantique des électrons dans une mémoire d’ordinateur conventionnelle, plus de $130$ Go de mémoire seraient nécessaires !  C’est considérable, mais à la portée de certains ordinateurs.  Si nous permettons aux particules d’être dans n’importe laquelle de $41$ positions, il y aurait deux fois plus de configurations à $2^{41}$ qui, à leur tour, nécessiteraient plus de $260$ Go de mémoire pour stocker l’état quantique. Ce jeu consistant à augmenter le nombre de positions ne peut pas être joué indéfiniment si nous voulons stocker l’état de manière conventionnelle, car nous dépassons rapidement les capacités de mémoire des machines les plus puissantes au monde.  À quelques centaines d’électrons, la mémoire requise pour stocker le système dépasse le nombre de particules dans l’univers. Par conséquent, il n’existe aucun espoir que nos ordinateurs conventionnels simulent jamais leur dynamique quantique. Et pourtant, dans la nature, de tels systèmes évoluent facilement dans le temps selon les lois de la mécanique quantique, inconscients de l’incapacité de concevoir et de simuler leur évolution avec la puissance informatique conventionnelle.

Cette observation a conduit ceux qui avaient une première vision de l’informatique quantique à se poser une question simple mais percutante : pouvons-nous faire de cette difficulté une opportunité ?  Plus précisément, si la dynamique quantique est difficile à simuler, que se passerait-il si nous construisions du matériel qui aurait des effets quantiques pour opérations fondamentales ?  Pourrions-nous simuler des systèmes de particules en interaction en utilisant un système qui exploite exactement les mêmes lois qui les gouvernent naturellement ? Pourrions-nous étudier des tâches qui sont totalement absentes de la nature, mais qui suivent des lois de la mécanique quantique ou en bénéficient ?  Ces questions ont donné naissance à l’informatique quantique.

Le cœur de l’informatique quantique est de stocker des informations dans des états quantiques de la matière et d’utiliser des opérations de portes quantiques pour effectuer des calculs sur ces informations, en exploitant les interférences quantiques et en apprenant à les « programmer ».  Un premier exemple d’interférence de programmation pour résoudre un problème considéré comme difficile pour nos ordinateurs conventionnels a été réalisé par [Peter Shor](https://en.wikipedia.org/wiki/Peter_Shor) en 1994 pour un problème connu sous le nom de factorisation.  La résolution de la factorisation permet à l’informatique de casser un grand nombre de nos systèmes de chiffrement à clé publique qui sous-tendent la sécurité du commerce électronique d’aujourd’hui, y compris la méthode RSA et le chiffrement à courbe elliptique.  Depuis ce temps, des algorithmes rapides et efficaces de calcul quantique ont été développés pour plusieurs de nos tâches classiques difficiles : simulation de systèmes physiques en chimie, physique et science des matériaux, recherche dans une base de données non triée, résolution de systèmes d’équations linéaires et apprentissage automatique.

Concevoir un programme quantique pour exploiter l’interférence peut sembler un défi de taille, et bien qu’il le soit, de nombreuses techniques et outils, dont notre Microsoft Quantum Development Kit, ont été introduits pour rendre la programmation quantique et le développement d’algorithmes plus accessibles. Il existe une poignée de stratégies de base qui peuvent être utilisées pour manipuler l’interférence quantique d’une manière utile pour le calcul, tout en évitant que la solution ne se perde dans un enchevêtrement de possibilités quantiques. La programmation quantique est une illustration distincte de la programmation classique nécessitant des outils très différents pour comprendre et exprimer la pensée algorithmique quantique. En effet, sans outils généraux pour aider un développeur quantique à aborder l’art de la programmation quantique, le développement algorithmique quantique n’est pas si simple.

Nous présentons le Microsoft Quantum Development Kit pour permettre à une communauté grandissante de disposer d’outils pour déverrouiller la révolution quantique pour ses tâches, problèmes, et solutions. Notre langage de programmation de haut niveau, Q#, a été conçu pour relever les défis du traitement de l’information quantique. Il est intégré dans une pile logicielle qui permet de compiler un algorithme quantique jusqu’aux opérations primitives d’un ordinateur quantique.  Avant d’aborder le langage de programmation, il est utile de passer en revue les principes de base sur lesquels repose l’informatique quantique. Nous considérerons les règles fondamentales de l’informatique quantique comme des axiomes, plutôt que de détailler leurs principes de base en mécanique quantique. De plus, nous supposerons une connaissance de base de l’algèbre linéaire (vecteurs, matrices, etc.). Si vous souhaitez faire une étude plus approfondie de l’histoire et des principes de l’informatique quantique, nous vous invitions à consulter la [section de référence](xref:microsoft.quantum.more-information) contenant plus d’informations.