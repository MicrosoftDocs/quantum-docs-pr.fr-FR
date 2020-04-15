---
title: Introduction au package de Machine Learning quantique | Microsoft Docs
description: Introduction au package de Machine Learning quantique
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907849"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Introduction à la bibliothèque de Machine Learning quantique

La bibliothèque de Machine Learning quantique est une API, écrite en Q#, qui vous permet d’exécuter des expériences de Machine Learning quantique/classique hybride. La bibliothèque vous permet d’effectuer les opérations suivantes :

- Charger vos propres données à classifier avec des simulateurs quantiques

- Utiliser des exemples et des tutoriels pour vous familiariser avec le secteur du Machine Learning quantique

Attendez-vous à de faibles performances par rapport aux frameworks de Machine Learning classique (n’oubliez pas que la charge de travail s’exécute sur la simulation d’un appareil quantique qui consomme beaucoup de ressources).

Les objectifs de cette documentation sont les suivants :

- Présenter de manière concise les outils de Machine Learning (écrits en Q\#) pour le Machine Learning quantique/classique hybride.
- Introduire les concepts de Machine Learning, en particulier leur réalisation dans les classifieurs quantiques centrés sur le circuit (également appelés classificateurs quantiques séquentiels).
- Fournir un ensemble de tutoriels sur les principes de base à connaître avant d’utiliser les outils fournis par la bibliothèque.
- Discuter des méthodes d’entraînement et de validation pour ces classifieurs et voir comment elles sont traduites en opérations Q\# spécifiques fournies par la bibliothèque.

Le modèle implémenté dans cette bibliothèque est basé sur le schéma d’entraînement quantique-classique présenté dans les [classifieurs quantiques centrés sur le circuit](https://arxiv.org/abs/1804.00633)
