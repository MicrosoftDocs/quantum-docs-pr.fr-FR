---
title: Guide de l’utilisateurQ#
description: Vue d’ensemble de l’objectif et du contenu du Guide de l’utilisateur
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231755"
---
# <a name="the-no-locq-user-guide"></a>Guide de l’utilisateurQ#

Bienvenue dans le Guide de l’utilisateur Q# ! 

Dans les différentes rubriques de ce guide, nous présentons quelques bases du développement de programmes quantiques avec Q#.

Nous nous référons au [Guide du langage Q#](xref:microsoft.quantum.qsharp.index) pour obtenir une spécification complète et une documentation sur le langage de programmation quantique Q#. 

## <a name="user-guide-contents"></a>Contenu du Guide de l’utilisateur

- [Programmes Q#](xref:microsoft.quantum.guide.programs): Présentation rapide des programmes quantiques dans Q#. 

- [Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs) : explique comment est exécuté un programme Q# et présente les différentes façons d’appeler le programme, à savoir, à partir de la ligne de commande, dans les notebooks Jupyter Q# ou à partir d’un programme hôte classique écrit en Python ou en langage .NET.

- [Test et débogage](xref:microsoft.quantum.guide.testingdebugging) : présente en détail certaines techniques vous permettant de vérifier que votre code fait ce qu’il est censé faire. 
    En raison de l’opacité générale des informations quantiques, le débogage d’un programme quantique peut nécessiter des techniques spécialisées. 
    Heureusement, Q# prend en charge la plupart des techniques de débogage classiques bien connues des programmeurs en plus de celles spécifiques au domaine quantique. Citons par exemple la création et l’exécution de tests unitaires dans Q#, l’incorporation d’*assertions* sur des valeurs et des probabilités dans votre code, ainsi que les fonctions `Dump` qui génèrent les états des ordinateurs cibles. 
    Ces derniers peuvent être utilisés avec notre simulateur d’état complet pour déboguer certaines parties des calculs en contournant des limitations quantiques (par exemple, le théorème d’[impossibilité du clonage](xref:microsoft.quantum.concepts.pauli)).

### <a name="quantum-simulators-and-resource-estimators"></a>Simulateurs quantiques et estimateurs de ressources

- [Simulateurs quantiques et applications hôtes](xref:microsoft.quantum.machines) : vue d’ensemble des différents simulateurs disponibles et de la manière dont les programmes hôtes et les ordinateurs cibles fonctionnent ensemble pour exécuter les programmes Q#.

- [Simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) : ordinateur cible qui simule l’état quantique complet. Utile pour l’exécution ou le débogage complet de programmes à plus petite échelle (moins de quelques dizaines de qubits)

- [Estimateur de ressources](xref:microsoft.quantum.machines.resources-estimator) : estime les ressources nécessaires pour exécuter une instance donnée d’une opération Q# sur un ordinateur quantique.

- [Simulateur de trace](xref:microsoft.quantum.machines.qc-trace-simulator.intro) : exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique et peut donc exécuter des programmes quantiques qui utilisent des milliers de qubits. Utile pour le débogage de code classique au sein d’un programme quantique ainsi que pour l’estimation des ressources requises.

- [Simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) : simulateur quantique à usage spécifique qui peut être utilisé avec des millions de qubits, mais uniquement pour les programmes avec un ensemble limité d’opérations quantiques (X, CNOT et X multicontrôlées).

### <a name="quick-reference-pages"></a>Pages de référence rapide

- [Commandes magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp) : page de référence rapide pour les commandes IQ# magic dans les notebooks Jupyter Q#.
