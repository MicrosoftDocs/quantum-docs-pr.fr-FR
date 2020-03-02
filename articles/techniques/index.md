---
title: Techniques de développement quantique
description: Découvrez les principes de base du développement de programmes Q#, utilisez des opérations, des fonctions, des variables et des qubits, puis créez un programme quantique simple.
keywords: N’ajoutez pas ou ne modifiez pas de mots clés sans consulter votre expert SEO.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907713"
---
# <a name="quantum-development-techniques"></a>Techniques de développement quantique

Cette section de notre documentation détaille les concepts de base utilisés pour créer des programmes quantiques en Q# et pour interagir avec ces programmes à partir d’applications classiques.
Nous partons du principe que vous avez une *certaine* connaissance des concepts de l’informatique quantique, comme ceux décrits dans [Concepts de l’informatique quantique](xref:microsoft.quantum.concepts.intro). Toutefois, il n’est pas nécessaire que vous soyez un expert en informatique quantique pour tirer parti de ces sections.

Leur contenu est le suivant.

- [Vue d’ensemble d’un programme Q#](xref:microsoft.quantum.techniques.file-structure) présente l’objectif et les fonctionnalités du langage de programmation Q#. 
    Cette section clarifie notamment le fait que Q# *n’est pas* un langage servant simplement à simuler la mécanique quantique, bien que cette fonctionnalité soit bien entendu fournie par notre simulateur d’état complet. 
    En fait, de par sa conception, Q# est tourné vers l’avenir et ses programmes décrivent comment un ordinateur de contrôle classique *interagit* avec des qubits. 

- [Opérations et fonctions](xref:microsoft.quantum.techniques.opsandfunctions) détaille les deux types du langage Q# qu’il est possible d’appeler : les *opérations* (qui incluent des actions sur les qubits et les systèmes quantiques) et les *fonctions* (qui fonctionnent strictement avec des informations classiques). 
    Il est essentiel que les informations classiques et quantiques fonctionnent en tandem ; sinon, l’informatique quantique est hors de portée. 
    Cette section décrit comment définir et utiliser ces éléments pouvant être appelés dans le flux de contrôle d’un programme Q#.

- [Variables locales](xref:microsoft.quantum.techniques.local-variables) décrit le rôle des variables dans les programmes Q# et comment les exploiter efficacement. 
    Vous découvrirez notamment la différence entre les variables modifiables/non modifiables et comment les affecter/réaffecter.

- [Utilisation des qubits](xref:microsoft.quantum.techniques.qubits) décrit les fonctionnalités de Q# que vous pouvez utiliser pour traiter des qubits individuels et des systèmes de qubits. 
    Plus précisément, vous apprendrez à les allouer, à leur appliquer des opérations et finalement à les mesurer. 
    Vous aborderez également des techniques de flux de contrôle utiles.

- Dans [Récapitulatif](xref:microsoft.quantum.techniques.puttingittogether), vous exploiterez les techniques décrites dans les sections ci-dessus pour créer un programme de **téléportation quantique** qui utilise deux bits classiques pour « téléporter » l’état complet d’un qubit vers un autre.

- [Pour aller plus loin](xref:microsoft.quantum.techniques.going-further) présente des techniques avancées qui peuvent s’avérer utiles à mesure que votre programmation quantique devient plus complexe. 
    Nous abordons en particulier l’utilisation d’opérations et de fonctions avec des *types paramétrables* dans Q#. Leur indépendance vis-à-vis des types spécifiques de leur entrée/sortie et leur capacité à *emprunter* des qubits permettent de mettre en place un flux de contrôle d’ordre supérieur. 
    L’emprunt est différent de l’allocation de base des qubits en ce sens qu’une opération Q# peut utiliser des qubits « incomplets », c’est-à-dire des qubits qui ne sont pas nécessairement initialisés à un état connu, pour faciliter les calculs.

- [Tests et débogage](xref:microsoft.quantum.techniques.testing-and-debugging) présente en détail certaines techniques vous permettant de vérifier que votre code fait ce qu’il est censé faire. 
    En raison de l’opacité générale des informations quantiques, le débogage d’un programme quantique peut nécessiter des techniques spécialisées. 
    Heureusement, Q# prend en charge la plupart des techniques de débogage classiques bien connues des programmeurs en plus de celles spécifiques au domaine quantique. Citons par exemple la création et l’exécution de tests unitaires dans Q#, l’incorporation d’*assertions* sur des valeurs et des probabilités dans votre code, ainsi que les fonctions `Dump` qui génèrent l’état de l’ordinateur cible. 
    Ce dernier peut être utilisé avec notre simulateur d’état complet pour déboguer certaines parties des calculs en contournant certaines limitations quantiques (par exemple, le théorème d’impossibilité du clonage).


![Quantum](~/media/mobius_strip_preview.png)
