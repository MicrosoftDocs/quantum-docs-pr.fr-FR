---
title: Guide de l’utilisateur Q#
description: Vue d’ensemble de l’objectif et du contenu du Guide de l’utilisateur
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430609"
---
# <a name="the-q-user-guide"></a>Guide de l’utilisateur Q#

Bienvenue dans le Guide de l’utilisateur Q# ! 

Nous allons ici détailler les concepts de base du langage Q# et toutes les informations dont vous avez besoin pour écrire des programmes quantiques.

## <a name="user-guide-contents"></a>Contenu du Guide de l’utilisateur

- [Concepts Q# de base](xref:microsoft.quantum.guide.basics) : vue d’ensemble d’introduction de l’objectif et des fonctionnalités du langage de programmation Q#. 

### <a name="q-language"></a>Langage Q#

- [Types en Q#](xref:microsoft.quantum.guide.types) : présente le modèle de type Q# et décrit la syntaxe permettant de spécifier et d’utiliser les types.

- [Expressions du type](xref:microsoft.quantum.guide.expressions) : explique comment spécifier, référencer, combiner et utiliser les valeurs de chaque type en Q#. 

### <a name="using-q"></a>Utilisation de Q#

- [Structure de fichiers Q#](xref:microsoft.quantum.guide.filestructure) : décrit la structure et la syntaxe d’un fichier `*.qs` Q#.

- [Opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions) : détaille les deux types pouvant être appelés du langage Q# : les *opérations* (qui incluent une action sur les registres qubit) et les *fonctions* (qui fonctionnent strictement avec des informations classiques). 
    Vous voyez ici comment les définir et les appeler, notamment les versions adjacentes et contrôlées des opérations quantiques.

- [Variables](xref:microsoft.quantum.guide.variables) : décrit le rôle des variables dans les programmes Q# et comment les exploiter efficacement. 
    Par exemple, vous pouvez trouver des informations sur les portées de liaison ainsi que la différence entre les variables mutables/immuables et comment les assigner/réassigner.

- [Utilisation des qubits](xref:microsoft.quantum.guide.qubits) : décrit les fonctionnalités de Q# qui permettent de traiter des qubits individuels et des systèmes de qubits. 
    Plus précisément, vous apprendrez à les allouer, à leur appliquer des opérations et finalement à les mesurer. 

- [Flux de contrôle](xref:microsoft.quantum.guide.controlflow) : décrit les modèles de flux de contrôle de programmation disponibles dans Q#, notamment de nombreuses techniques standard (exécution conditionnelle, boucles for, boucles while, etc.) ainsi que le modèle « répéter-jusqu’à-réussite » spécifique au domaine quantique.

- [Tests et débogage](xref:microsoft.quantum.guide.testingdebugging) : présente en détail certaines techniques vous permettant de vérifier que votre code fait ce qu’il est censé faire. 
    En raison de l’opacité générale des informations quantiques, le débogage d’un programme quantique peut nécessiter des techniques spécialisées. 
    Heureusement, Q# prend en charge la plupart des techniques de débogage classiques bien connues des programmeurs en plus de celles spécifiques au domaine quantique. Citons par exemple la création et l’exécution de tests unitaires dans Q#, l’incorporation d’*assertions* sur des valeurs et des probabilités dans votre code, ainsi que les fonctions `Dump` qui génèrent l’état de l’ordinateur cible. 
    Ce dernier peut être utilisé avec notre simulateur d’état complet pour déboguer certaines parties des calculs en contournant des limitations quantiques (par exemple, le théorème d’impossibilité du clonage).

### <a name="quantum-simulators-and-resource-estimators"></a>Simulateurs quantiques et estimateurs de ressources

- [Simulateurs quantiques et applications hôtes](xref:microsoft.quantum.machines) : vue d’ensemble des différents simulateurs disponibles avec le modèle d’exécution générale entre le programme hôte et les ordinateurs cibles.

- [Simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) : ordinateur cible qui simule l’état quantique complet. Utile pour l’exécution ou le débogage complet de programmes à plus petite échelle (moins de quelques douzaines de qubits)

- [Estimateur de ressources](xref:microsoft.quantum.machines.resources-estimator) : estime les ressources nécessaires pour exécuter une instance donnée d’une opération Q# sur un ordinateur quantique.

- [Simulateur de trace](xref:microsoft.quantum.machines.qc-trace-simulator.intro) : exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique et peut par conséquent exécuter des programmes quantiques qui utilisent des milliers de qubits. Utile pour le débogage de code classique au sein d’un programme quantique ainsi que pour l’estimation des ressources requises.

- [Simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) : simulateur quantique à usage spécifique qui peut être utilisé avec des millions de qubits, mais uniquement pour les programmes avec un ensemble limité d’opérations quantiques (à savoir X, CNOT et X multicontrôlées).

### <a name="quick-reference-pages"></a>Pages de référence rapide

- [Commandes IQ# Magic](xref:microsoft.quantum.guide.quickref.iqsharp) : page de référence rapide pour les commandes IQ# Magic dans les notebooks Jupyter Q#.
