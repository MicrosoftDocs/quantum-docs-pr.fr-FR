---
title: Découvrir comment installer le Microsoft Quantum Development Kit (QDK)
description: Découvrez comment installer le kit de développement Microsoft Quantum pour les environnements C#, Python et Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680196"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installer le Microsoft Quantum Development Kit (QDK)

Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique. Le QDK se compose des éléments suivants :

- le langage de programmation Q#
- un ensemble de bibliothèques qui ont abstrait des fonctionnalités complexes en Q#
- API pour Python et les langages .NET (C#, F# et VB.NET) pour exécuter des programmes quantiques écrits en Q#
- des outils pour faciliter votre développement

Les programmes Q# sont souvent associés à un programme hôte écrit dans un langage .NET (en général C#) ou Python. Cela nous permet d’appeler des opérations quantiques à partir d’un programme classique.
QDK fournit également la prise en charge de Q# pour Jupyter Notebook avec le noyau Jupyter IQ#.

Le QDK est disponible pour plusieurs environnements de développement. Sélectionnez votre configuration préférée dans les sections ci-dessous :

- [Application en ligne de commande Q#](xref:microsoft.quantum.install.standalone) : choisissez cette approche si vous souhaitez utiliser Q# à partir de la ligne de commande. Vous n’avez pas besoin d’un pilote ni d’un programme hôte comme avec les options ci-dessous.
- [Installer Q# pour Jupyter Notebook](xref:microsoft.quantum.install.jupyter) : choisissez cet environnement pour exécuter du code Q# dans des cellules avec du texte incorporé ou créer des tutoriels interactifs sur l’informatique quantique. 
- [Développer avec Q# et Python](xref:microsoft.quantum.install.python) : si vous souhaitez combiner Python et Q# pour créer un programme hôte Python qui appelle des opérations Q#.
- [Développer avec Q# et C# ou F#](xref:microsoft.quantum.install.cs) : si vous souhaitez combiner C# ou F# et Q# pour créer un programme hôte .NET qui appelle des opérations Q#.
