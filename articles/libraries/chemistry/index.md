---
title: Introduction au package Chimie quantique | Microsoft Docs
description: Introduction au package Chimie quantique
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: e5a9dd70874f1ae0baf4b781346278195a980a7e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960425"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introduction à la bibliothèque de chimie quantique

La simulation de systèmes physiques a longtemps joué un rôle central dans l’informatique quantique.  La raison en est que la dynamique quantique est largement considérée comme réfractaire à la simulation sur des ordinateurs quantiques, ce qui signifie que la complexité de la simulation du système s’accroît de façon exponentielle avec la taille du système quantique en question.  La simulation des problèmes dans les domaines de la chimie et de la science des matériaux reste peut-être l’application la plus évocatrice de l’informatique quantique, et nous permettrait d’investiguer des mécanismes de réaction chimique qui étaient jusqu’ici au-delà de notre capacité à les mesurer ou à les simuler.  Elle nous permettrait également de simuler des matériaux électroniques corrélés, comme les supraconducteurs à haute température. La liste des applications de cet espace est vaste.

L’objectif de cette documentation est de fournir une introduction concise à la simulation des problèmes de structure électronique sur les ordinateurs quantiques, afin d’aider le lecteur à comprendre le rôle joué par de nombreux aspects de la bibliothèque de simulation hamiltonienne dans l’espace.  Nous commençons par une brève présentation des mécanismes quantiques, puis nous expliquons comment les systèmes électroniques y sont modélisés.  Nous décrivons ensuite comment ces dynamiques quantiques peuvent être émulées avec un ordinateur quantique.  Après cela, nous présentons deux méthodes utilisées pour compiler les dynamiques quantiques en séquences de portes élémentaires : Décompositions de Trotter-Suzuki et qubitisation.