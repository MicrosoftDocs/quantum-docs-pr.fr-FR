---
title: Introduction à la bibliothèque de chimie quantique
description: Découvrez la bibliothèque de chimie quantique Microsoft et la façon dont elle est utilisée pour simuler des problèmes de structure électronique sur des ordinateurs quantiques.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3fa606600db1641b9f8b86ccefebb7681f181b92
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847482"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introduction à la bibliothèque de chimie quantique

La simulation de systèmes physiques a longtemps joué un rôle central dans l’informatique quantique.  La raison en est que la dynamique quantique est largement considérée comme réfractaire à la simulation sur des ordinateurs quantiques, ce qui signifie que la complexité de la simulation du système s’accroît de façon exponentielle avec la taille du système quantique en question.  La simulation des problèmes dans les domaines de la chimie et de la science des matériaux reste peut-être l’application la plus évocatrice de l’informatique quantique, et nous permettrait d’investiguer des mécanismes de réaction chimique qui étaient jusqu’ici au-delà de notre capacité à les mesurer ou à les simuler.  Elle nous permettrait également de simuler des matériaux électroniques corrélés, comme les supraconducteurs à haute température. La liste des applications de cet espace est vaste.

L’objectif de cette documentation est de fournir une introduction concise à la simulation des problèmes de structure électronique sur les ordinateurs quantiques, afin d’aider le lecteur à comprendre le rôle joué par de nombreux aspects de la bibliothèque de simulation hamiltonienne dans l’espace.  Nous commençons par une brève présentation des mécanismes quantiques, puis nous expliquons comment les systèmes électroniques y sont modélisés.  Nous décrivons ensuite comment ces dynamiques quantiques peuvent être émulées avec un ordinateur quantique.  Après cela, nous présentons deux méthodes utilisées pour compiler les dynamiques quantiques en séquences de portes élémentaires : Décompositions de Trotter-Suzuki et qubitisation.
