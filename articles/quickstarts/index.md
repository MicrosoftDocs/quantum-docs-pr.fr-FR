---
title: Installer le Microsoft Quantum Development Kit (QDK)
description: Guide pratique pour installer le Microsoft Quantum Development Kit pour différents environnements.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863706"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Installer le Microsoft Quantum Development Kit (QDK)

Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique. Le QDK se compose des éléments suivants :

- Langage de programmation Q#
- Ensemble de bibliothèques qui résument des fonctionnalités complexes en Q#
- API pour Python et les langages .NET (C#, F# et VB.NET) pour exécuter des programmes quantiques écrits en Q#
- Outils pour faciliter votre développement

Les programmes Q# peuvent être exécutés en tant qu’applications autonomes à l’aide de Visual Studio Code ou Visual Studio, ou via des notebooks Jupyter avec le noyau Jupyter IQ#.
Ils peuvent également être associés à un programme hôte écrit dans un langage .NET (généralement C#) ou Python, ce qui vous permet d’appeler des opérations quantiques à partir d’un programme classique.

Le workflow de chacune de ces configurations est décrit et comparé aux autres dans [Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs).

Pour procéder à l’installation du QDK et à la création de projets Q#, sélectionnez votre configuration préférée :

[Développer avec des Q#applications](xref:microsoft.quantum.install.standalone) : choisissez cette approche pour utiliser Q# à partir de l’invite de commande. Vous n’avez pas besoin d’un pilote ni d’un programme hôte comme avec les options ci-dessous.

[Développer avec des notebooks Jupyter Q#](xref:microsoft.quantum.install.jupyter) : choisissez cet environnement pour exécuter du code Q# dans des cellules avec du texte incorporé ou créer des tutoriels interactifs sur l’informatique quantique. 

[Développer avec Q# et Python](xref:microsoft.quantum.install.python) : cette option vous permet de combiner Python et Q# afin de créer un programme hôte Python qui appelle des opérations Q#.

[Développer avec Q# et .NET](xref:microsoft.quantum.install.cs) : combinez C#, F# ou VB.NET avec Q# pour créer un programme hôte .NET qui appelle des opérations Q#.
