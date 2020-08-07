---
title: Introduction à la bibliothèque de valeurs numériques de quantum | Microsoft Docs
description: Introduction à la bibliothèque de valeurs numériques de quantum
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: dc6407d9775ad8a401036912abd0b70033796144
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868778"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>Introduction à la bibliothèque de valeurs numériques de quantum

De nombreux algorithmes de quantum reposent sur [oracles](xref:microsoft.quantum.concepts.oracles) qui évaluent les fonctions mathématiques sur une superposition d’entrées.
Le composant principal de l’algorithme de Shori, par exemple, évalue $f(x) = a^x\operatorname{mod} N$ pour un $a$ fixe, le nombre à factoriser $N$ et $x$ a entier $2n$-qubit dans une superposition uniforme sur toutes les chaînes de $2n$ bits.

Pour exécuter l’algorithme de Shori sur un ordinateur de quantum réel, cette fonction doit être écrite en termes d’opérations natives de l’ordinateur cible.
À l’aide de la représentation binaire de $x$ avec $x_i $ désignant le $i$-ème compte de bits du bit le moins significatif, $f(x)$ peut être écrit comme $f(x) = a^{\sum_{i = 0}^{2n-1}x_i 2^i} \operatorname{mod} N $.
À son tour, ce peut être écrit en tant que produit (mod N) des termes $a^{2^i x_i} = (a^{2^i})^{x_i}$. La fonction $f(x)$ peut donc être implémentée à l’aide d’une séquence de démultiplications de $2n$ (modulaires) par $a^{2^i}$ conditionnel sur $x_i$ étant différent de zéro. Les constantes $a^{2^i}$ peuvent être précalculées et réduites sur le modulo N avant d’exécuter l’algorithme.

Cette séquence de multiplications modulaires contrôlées peut être ultérieurement simplifiée : Chaque multiplication peut être effectuée à l’aide d’une séquence d’ajouts modulaires contrôlés par $n$ ; chaque ajout modulaire peut être créé à partir d’un ajout régulier et d’un comparateur.


Étant donné qu’un grand nombre d’étapes sont nécessaires pour arriver à une implémentation réelle, il serait extrêmement utile d’avoir de telles fonctionnalités disponibles dès le début.
C’est pourquoi le Quantum Development kit prend en charge un large éventail de fonctionnalités numériques.


## <a name="functionality"></a>Fonctionnalités

Outre les opérations arithmétiques sur les entiers mentionnées jusqu’à présent, la bibliothèque numérique fournit

- Fonctionnalité entière (non)signée (multiplier, carré, division avec le reste, inversion,...) avec un ou deux nombres entiers de quantum comme entrée
- Fonctionnalité à point fixe (ajouter/soustraire, multiplier, carré, 1/x, évaluation polynomiale) avec un ou deux nombres à point fixe de quantum comme entrée

## <a name="getting-started"></a>Prise en main

> [!div class="nextstepaction"]
> [En savoir plus sur la bibliothèque de valeurs numériques](xref:microsoft.quantum.numerics.usage)
