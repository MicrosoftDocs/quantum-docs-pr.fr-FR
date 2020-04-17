---
title: Qu’est-ce que l’informatique quantique ?
description: Introduction aux fonctionnalités, aux algorithmes, au matériel et au kit de développement Microsoft Quantum (QDK) de l’informatique quantique.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 668df50882272bfa56541f178e2f4d5fb35efcf5
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906778"
---
# <a name="what-is-quantum-computing"></a>Qu’est-ce que l’informatique quantique ?

Certains problèmes sont si difficiles à résoudre et si incroyablement vastes que, même si tous les superordinateurs du monde travaillaient sur l’un d’eux, sa résolution prendrait plus de temps que l’existence de l’univers.

Les ordinateurs quantiques promettent de résoudre certains des plus grands défis auxquels notre planète est confrontée dans différents domaines : environnement, agriculture, santé, énergie, climat, science des matériaux et bien d’autres que nous ne pouvons pas encore imaginer. Les ordinateurs quantiques auront un impact considérable, comparable à l’incidence de l’invention du transistor en 1947, qui a ouvert la voie à l’économie numérique d’aujourd’hui.

L’informatique quantique tire parti des acquis uniques de la physique quantique pour fournir un modèle informatique nouveau et puissant. La théorie de la physique quantique postule que la matière, à un niveau quantique, peut se trouver dans une superposition de plusieurs états classiques. Ces états interfèrent entre eux, comme des vagues dans une mare résiduelle.  L’état de la matière après une mesure « retombe » dans l’un des états classiques. 

Par la suite, la répétition de la même mesure va produire le même résultat classique.  L’intrication quantique se produit quand des particules interagissent de telle manière que l’état quantique de chacune d’elles ne peut pas être décrit indépendamment des autres, même si les particules sont physiquement très éloignées.  

L’informatique quantique stocke des informations dans des états quantiques de la matière et utilise sa nature quantique de superposition et d’intrication pour réaliser des opérations quantiques qui effectuent des calculs sur ces informations, en exploitant et en apprenant ainsi à programmer les interférences quantiques.

L’informatique quantique peut sembler intimidante mais, avec des ressources appropriées, vous pouvez commencer à créer des applications quantiques aujourd’hui.

## <a name="the-qubit"></a>Le qubit

L’informatique quantique définit des concepts informatiques qui reflètent le comportement quantique.  L’informatique quantique commence avec la notion de qubit.  En informatique quantique, un bit quantique (**qubit**) est une unité d’information quantique, à la manière d’un bit classique. Alors que les bits classiques contiennent une seule valeur binaire comme 0 ou 1, l’état d’un qubit peut se trouver dans une **superposition** de 0 et de 1 simultanément.  

Le fait de mesurer un qubit modifie son état. Avec la mesure, le qubit passe de la superposition à l’un des états classiques.  

Plusieurs qubits peuvent également être **intriqués**. Quand nous mesurons un seul qubit intriqué, notre connaissance de l’état des autres qubits est également mise à jour.

## <a name="quantum-algorithms"></a>Algorithmes de quantum

Des algorithmes quantiques sont conçus pour tirer parti de la nature et du comportement quantiques afin d’accélérer les algorithmes classiques ou de fournir des méthodes entièrement nouvelles de modélisation des systèmes physiques.  Ces algorithmes exploitent la manière dont les qubits encodent les informations et la nature parallèle du fonctionnement sur plusieurs qubits intriqués dans la superposition.  

Les ordinateurs classiques encodent les informations dans des bits ; chaque bit encodant 2 valeurs possibles, 0 ou 1.  Un qubit encode deux valeurs simultanément, 0 et 1.  Deux bits classiques encodent une seule valeur parmi 4 possibles (00, 01, 10, 11) tandis que 2 qubits encodent toute superposition de ces 4 états simultanément, même si nous ne pouvons obtenir qu’une seule de ces valeurs lors de la mesure. Quatre qubits encodent toute superposition de 16 valeurs simultanément, et ainsi de suite, de façon exponentielle.  100 qubits peuvent encoder plus d’informations que celles disponibles dans les systèmes informatiques les plus gros d’aujourd’hui.  

De plus, quand plusieurs qubits intriqués agissent de manière cohérente, ils peuvent traiter plusieurs options simultanément. Les qubits intriqués peuvent traiter des informations en une fraction du temps qu’il faudrait aux systèmes non quantiques les plus rapides.

L’exploitation de ces attributs quantiques a été l’objectif de plusieurs décennies de recherche dans le domaine des algorithmes quantiques. De nombreuses techniques novatrices ont d’ailleurs été trouvées pour résoudre des problèmes en une fraction du temps qu’il aurait fallu avec des méthodes classiques.  

L’un des algorithmes quantiques les plus connus est l’_algorithme de Shor_ pour la factorisation, qui résout le problème classiquement inextricable de factorisation d’un grand nombre en deux nombres premiers assez rapidement pour défier la cryptographie traditionnelle.

Sur un plan plus constructif, les algorithmes de distribution sécurisée de clés de chiffrement sont rendus possibles par la superposition, l’intrication quantique et la nature **non clonable** des qubits, qui rendent impossible toute copie indétectable de qubits.

_L’algorithme de Grover_ met en avant une technique d’algorithme quantique qui fournit une accélération quadratique pour la recherche dans des données non structurées.

## <a name="quantum-hardware"></a>Matériel quantique

Dans les ordinateurs classiques, les bits correspondent à des niveaux de tension dans les circuits de silicium. Le matériel informatique quantique peut être implémenté par de nombreuses réalisations physiques de qubits : ions piégés, supraconduction, atomes neutres, résonance magnétique, polarisation de la lumière, qubits topologiques. Le matériel quantique est une technologie émergente. Les qubits sont fragiles par nature et deviennent moins cohérents à mesure qu’ils interagissent avec leur environnement. Cela nécessite un équilibre entre la fidélité et la scalabilité du système. Plus l’échelle (c’est-à-dire le nombre de qubits) est grande, plus le taux d’erreur est élevé.

Microsoft développe un ordinateur quantique basé sur des qubits topologiques. Nous pensons qu’un qubit topologique sera moins affecté par des modifications de son environnement, réduisant ainsi le degré de correction d’erreur externe. Les qubits topologiques se caractérisent par une stabilité accrue et une résistance au bruit ambiant. Cela signifie qu’ils peuvent adapter leur échelle plus facilement et rester fiables plus longtemps.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Informatique quantique : une pile matérielle et logicielle complète

Le programme quantique de Microsoft est unique en ce sens que nous nous concentrons sur l’ajustement de chaque composant du système pour produire un impact quantique réel. Cette approche complète implique :

* la création d’un ordinateur quantique à l’aide de qubits topologiques fiables, scalables et tolérants aux pannes, 
* l’ingénierie d’un plan de contrôle cryogénique unique avec une alimentation et une dissipation thermique faibles, 
* le développement d’une pile logicielle complète pour permettre la programmation de l’ordinateur quantique et le contrôle du système à l’échelle.

Le Quantum Development kit (QDK) open source a été introduit pour rendre la programmation quantique et le développement d’algorithmes plus accessibles. Notre langage de programmation général, Q#, relève les défis de la programmation quantique.  Nous avons conçu Q# comme un langage de programmation quantique général axé sur le développement d’algorithmes et d’applications. Le compilateur Q# est intégré à une pile logicielle qui permet à un algorithme quantique d’être compilé jusqu’aux opérations primitives d’un ordinateur quantique.  Jusqu’à une certaine échelle (nombre de qubits), l’informatique quantique peut être simulée sur un ordinateur classique. Une simulation vous permet de commencer à écrire des programmes quantiques aujourd’hui pour les exécuter demain sur du matériel quantique.  Nous avons également associé Q# à des exemples, des bibliothèques et des exercices pratiques pour commencer à utiliser la programmation quantique tout de suite. 

## <a name="next-steps"></a>Étapes suivantes

* [Que sont capables de faire les ordinateurs quantiques ?](xref:microsoft.quantum.overview.computers)
* [Prise en main du Quantum Development Kit de Microsoft](xref:microsoft.quantum.welcome)
* En savoir plus sur les [concepts de l’informatique quantique](xref:microsoft.quantum.concepts.intro)
