---
title: Introduction au package de Machine Learning quantique | Microsoft Docs
description: Introduction au package de Machine Learning quantique
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2f8884fafd6370e4f70ec93e6fc8617c34c29431
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868846"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="967af-103">Introduction à la bibliothèque de Machine Learning quantique</span><span class="sxs-lookup"><span data-stu-id="967af-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="967af-104">La bibliothèque de Machine Learning quantique est une API, écrite en Q#, qui vous permet d’exécuter des expériences de Machine Learning quantique/classique hybride.</span><span class="sxs-lookup"><span data-stu-id="967af-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="967af-105">La bibliothèque vous permet d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="967af-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="967af-106">Charger vos propres données à classifier avec des simulateurs quantiques</span><span class="sxs-lookup"><span data-stu-id="967af-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="967af-107">Utiliser des exemples et des tutoriels pour vous familiariser avec le secteur du Machine Learning quantique</span><span class="sxs-lookup"><span data-stu-id="967af-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="967af-108">Attendez-vous à de faibles performances par rapport aux frameworks de Machine Learning classique (n’oubliez pas que la charge de travail s’exécute sur la simulation d’un appareil quantique qui consomme beaucoup de ressources).</span><span class="sxs-lookup"><span data-stu-id="967af-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="967af-109">Les objectifs de cette documentation sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="967af-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="967af-110">Présenter de manière concise les outils de Machine Learning (écrits en Q\#) pour le Machine Learning quantique/classique hybride.</span><span class="sxs-lookup"><span data-stu-id="967af-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="967af-111">Introduire les concepts de Machine Learning, en particulier leur réalisation dans les classifieurs quantiques centrés sur le circuit (également appelés classificateurs quantiques séquentiels).</span><span class="sxs-lookup"><span data-stu-id="967af-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="967af-112">Fournir un ensemble de tutoriels sur les principes de base à connaître avant d’utiliser les outils fournis par la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="967af-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="967af-113">Discuter des méthodes d’entraînement et de validation pour ces classifieurs et voir comment elles sont traduites en opérations Q\# spécifiques fournies par la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="967af-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="967af-114">Le modèle implémenté dans cette bibliothèque est basé sur le schéma d’entraînement quantique-classique présenté dans les [classifieurs quantiques centrés sur le circuit](https://arxiv.org/abs/1804.00633)</span><span class="sxs-lookup"><span data-stu-id="967af-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
