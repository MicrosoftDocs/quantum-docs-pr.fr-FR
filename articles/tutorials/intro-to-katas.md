---
title: Introduction aux katas Quantum
description: En savoir plus sur les katas (exercices de formation) fournis avec le kit de développement Microsoft Quantum (QDK)
author: bradben
ms.author: v-benbra
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
no-loc:
- Q#
- $$v
ms.openlocfilehash: 097d7f70088b6ee84a1e91ee99be59149dd9e15b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834820"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Découvrez l’informatique quantique avec les katas quantiques

[Les katas Quantum](https://github.com/Microsoft/QuantumKatas/) sont des didacticiels Open source à votre rythme et des exercices de programmation destinés à enseigner en même temps les éléments de l’informatique Quantum et de la Q# programmation.

## <a name="learning-by-doing"></a>Apprendre par la pratique

Les tutoriels et les exercices réunis dans ce projet mettent l’accent sur l’apprentissage par la pratique : ils proposent des tâches de programmation couvrant des sujets qui vont de très simples à très complexes. Chaque tâche vous demande de renseigner du code, les premières peuvent ne nécessiter qu’une seule ligne alors que les dernières peuvent nécessiter un fragment de code assez grand.

Plus important encore, les katas incluent des frameworks de test qui configurent, exécutent et valident les solutions des tâches. Ainsi, vous pouvez obtenir des commentaires immédiats sur votre solution et reconsidérer votre approche si elle est incorrecte.

Vous pouvez utiliser les katas dans l’environnement de votre choix :

* Jupyter Notebooks en ligne dans l’environnement Binder
* Jupyter Notebooks s’exécutant sur votre ordinateur local
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Qu’est-ce que je peux apprendre avec les katas quantiques ?

Découvrez les concepts et les principes de base de l’informatique quantique, ou explorez en détail les algorithmes et les protocoles quantiques. Nous vous recommandons de suivre ce parcours d’apprentissage en premier pour veiller à bien maîtriser les concepts fondamentaux de l’informatique quantique. Bien sûr, vous pouvez ignorer les sujets que vous maîtrisez déjà, comme l’arithmétique complexe, et étudier les algorithmes dans l’ordre qui vous plaît.

### <a name="introduction-to-quantum-computing-concepts"></a>Présentation des concepts de l’informatique quantique

| Kata | Description |
|:-----|-------------|
|[Arithmétique complexe](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)|Ce tutoriel explique certaines notions mathématiques qui sont nécessaires à l’utilisation de l’informatique quantique, telles que les nombres imaginaires ou les nombres complexes.|
|[Algèbre linéaire](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)|L’algèbre linéaire est utilisée pour représenter les opérations et les états quantiques en informatique quantique. Ce tutoriel décrit les concepts de base, y compris les matrices et les vecteurs.|
|[Concept du qubit](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/Qubit)|Découvrez les qubits, qui sont au cœur de l’informatique quantique. |
|[Portes quantiques à qubit unique](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/SingleQubitGates)|Ce tutoriel présente les portes quantiques à qubit unique, qui sont les éléments constituants des algorithmes quantiques et permettent de transformer les états des qubits quantiques de différentes façons.|
|[Systèmes multiqubits](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/MultiQubitSystems)|Ce didacticiel présente les systèmes qubit, leur représentation en notation mathématique et dans Q# le code, ainsi que le concept d’enchevêtrement.|
|[Portes quantiques multiqubits](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/MultiQubitGates)|Ce tutoriel suit la même logique que le tutoriel [Portes quantiques à qubit unique](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/SingleQubitGates), mais il se concentre sur l’application des portes quantiques aux systèmes multiqubits.|

### <a name="quantum-computing-fundamentals"></a>Fondamentaux de l’informatique quantique

| Kata | Description |
|:-----|-------------|
|[Reconnaissance des portes quantiques](https://github.com/microsoft/QuantumKatas/tree/main/BasicGates)|Une série d’exercices conçus pour vous familiariser avec les portes quantique de base dans Q# . Comprend des exercices pour les portes à qubit unique, les portes multiqubits, les portes adjacentes et les portes contrôlées, ainsi que des exercices expliquant comment utiliser les portes pour modifier l’état d’un qubit.|
|[Création d’une superposition quantique](https://github.com/microsoft/QuantumKatas/tree/main/Superposition)|Utilisez ces exercices pour vous familiariser avec le concept de superposition et de programmation dans Q# . Comprend des exercices pour les portes qubit et qubit de base, la superposition et le contrôle de Flow et la récursivité dans Q# .|
|[Distinction des états quantiques à l’aide de mesures](https://github.com/microsoft/QuantumKatas/tree/main/Measurements)|Faites ces exercices pendant votre apprentissage de la mesure quantique, ainsi que des états orthogonaux et non orthogonaux. |
|[Mesures communes](https://github.com/microsoft/QuantumKatas/tree/main/JointMeasurements)|Découvrez les mesures de parité communes et comment utiliser l’opération [Measure](xref:microsoft.quantum.intrinsic.measure) pour distinguer les états quantiques.|

### <a name="algorithms"></a>Algorithmes

| Kata | Description |
|:-----|-------------|
|[Téléportation quantique](https://github.com/microsoft/QuantumKatas/tree/main/Teleportation)|Ce kata explore la téléportation quantique. Il s’agit d’un protocole qui permet de communiquer un état quantique en utilisant uniquement la communication classique et l’intrication quantique précédemment partagée.|
|[codage Superdense](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding)|Le codage super-dense est un protocole qui permet de transmettre deux bits d’informations classiques en envoyant un seul qubit à l’aide de l’intrication quantique précédemment partagée.  |
|[Algorithme de Deutsch-Jozsa](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ExploringDeutschJozsaAlgorithm)|Cet algorithme est connu pour être l’un des premiers exemples d’algorithmes quantiques qui sont exponentiellement plus rapides que n’importe quel algorithme déterministe classique.|
|[Exploration des propriétés générales de l’algorithme de recherche de Grover](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ExploringGroversAlgorithm)|Présentation de l’un des algorithmes les plus connus en informatique quantique. Celui-ci résout le problème consistant à trouver une entrée dans une boîte noire (oracle) qui produit une sortie particulière. |
|[Implémentation de l’algorithme de recherche de Grover](https://github.com/microsoft/QuantumKatas/tree/main/GroversAlgorithm)|Ce kata explore plus en détail l’algorithme de recherche de Grover, et traite de l’écriture d’oracles, de l’exécution des étapes de l’algorithme, et enfin, de l’utilisation conjointe de tous ces éléments.|
|[Résolution de problèmes réels à l’aide de l’algorithme de Grover : Problèmes SAT](https://github.com/microsoft/QuantumKatas/tree/main/SolveSATWithGrover)|Série d’exercices qui utilisent l’algorithme de Grover pour résoudre des problèmes réalistes, en prenant comme exemple les [problèmes SAT](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem).  |
|[Résolution de problèmes réels à l’aide de l’algorithme de Grover : Problèmes de coloration des graphes](https://github.com/microsoft/QuantumKatas/tree/main/GraphColoring)| Ce kata explore plus en détail l’algorithme de Grover, qui permet de résoudre les [problèmes de satisfaction des contraintes](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem), en prenant comme exemple un problème de coloration des graphes. |

### <a name="protocols-and-libraries"></a>Protocoles et bibliothèques

| Kata | Description |
|:-----|-------------|
|[Protocole BB84 pour la distribution de clés quantique](https://github.com/microsoft/QuantumKatas/tree/main/KeyDistribution_BB84)|Découvrez comment implémenter un protocole de distribution de clés quantiques ([BB84](https://en.wikipedia.org/wiki/BB84)) à l’aide de qubits pour échanger des clés de chiffrement. |
|[Code de correction d’erreurs d’inversion de bits](https://github.com/microsoft/QuantumKatas/tree/main/QEC_BitFlipCode)|Découvrez la correction des erreurs quantiques avec le plus simple des codes de correction des erreurs quantiques : le code d’inversion de bits à trois qubits.|
|[Estimation des phases](https://github.com/microsoft/QuantumKatas/blob/main/PhaseEstimation)|Les algorithmes d’estimation de phase sont parmi les éléments les plus fondamentaux de l’informatique quantique. En savoir plus sur l’estimation de la phase avec ces exercices qui couvrent l’estimation de la phase Quantum et la préparation et l’exécution des routines d’estimation des phases dans Q# .|
|[Arithmétique quantique : Création d’additionneurs séquentiels](https://github.com/microsoft/QuantumKatas/blob/main/RippleCarryAdder)|Série d’exercices avancés qui explorent les additions [séquentielles](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) (ripple-carry) sur un ordinateur quantique. Créez un additionneur quantique sur place, développez-le avec un autre algorithme, puis générez un soustracteur quantique sur place.   |

### <a name="entanglement-games"></a>Jeux d’intrication

| Kata | Description |
|:-----|-------------|
|[Jeu CHSH](https://github.com/microsoft/QuantumKatas/tree/main/CHSHGame)|Explorez l’intrication quantique avec une implémentation du jeu [CHSH](https://en.wikipedia.org/wiki/CHSH_inequality). Ce jeu [non local](https://en.wikipedia.org/wiki/Quantum_refereed_game) montre comment l’intrication quantique peut être utilisée pour augmenter les chances de gagner, au-delà de ce qui serait possible avec une stratégie entièrement classique.|
|[Jeu GHZ](https://github.com/microsoft/QuantumKatas/tree/main/GHZGame)|Le jeu GHZ est un autre jeu non local, mais il implique trois joueurs.|
|[Jeu du carré magique de Peres et Mermin](https://github.com/microsoft/QuantumKatas/tree/main/MagicSquareGame)|Série d’exercices qui explorent la [pseudo-télépathie quantique](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) pour résoudre un jeu de carré magique.  |

## <a name="resources"></a>Ressources

Voir la série complète des [katas quantiques](https://github.com/microsoft/QuantumKatas)

[Exécuter les katas en ligne](https://aka.ms/try-quantum-katas)
