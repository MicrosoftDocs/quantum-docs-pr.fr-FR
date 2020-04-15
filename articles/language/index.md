---
title: Le langage de programmation Q#
description: Introduction au langage Q# pour le développement de programmes quantiques.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: b62e6866fc3609d95c26a5eab2a6eac325dfe330
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907373"
---
# <a name="the-q-programming-language"></a>Le langage de programmation Q#

## <a name="introduction"></a>Introduction

Un modèle naturel de calcul quantique consiste à traiter l’ordinateur quantique comme un coprocesseur, semblable à celui utilisé pour les GPU, les FPGA et autres processeurs auxiliaires.
La logique de commande primaire exécute le code classique sur un ordinateur « hôte » classique.
Le cas échéant, le programme hôte peut invoquer un sous-programme qui s’exécute sur le processeur auxiliaire.
À la fin du sous-programme, le programme hôte obtient l’accès aux résultats du sous-programme.

Q# (Q-sharp) est un langage de programmation spécifique au domaine utilisé pour exprimer les algorithmes quantiques.
Il doit être utilisé pour écrire des sous-programmes qui s’exécutent sur un processeur quantique auxiliaire, sous le contrôle d’un ordinateur et d’un programme hôte classiques.
Tant que les processeurs quantiques ne sont pas largement disponibles, les sous-programmes Q# s’exécutent sur un simulateur.

Q# fournit un petit ensemble de types primitifs, ainsi que deux méthodes (tableaux et tuples) pour créer de nouveaux types structurés.
Il prend en charge un modèle procédural de base pour l’écriture de programmes, avec des boucles et des instructions IF/THEN.
Les constructions de niveau supérieur en Q# sont des types, des opérations et des fonctions définis par l’utilisateur.

Les sections suivantes décrivent en détail :
- [Modèle de type](xref:microsoft.quantum.language.type-model)
- [Expressions](xref:microsoft.quantum.language.expressions)
- [Instructions](xref:microsoft.quantum.language.statements)
- [Structure de fichiers](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a>Conventions

Nous veillons à ce que des signes de ponctuation communs soient utilisés de façon uniforme dans toutes les situations.
Nous pensons que cela rendra Q# plus facile à apprendre et à lire, car ces marques signifient toujours la même chose et le même concept est toujours représenté de la même façon.

Plus précisément :

- Le point-virgule, `;`, est utilisé pour terminer une instruction ou une directive à une ligne.
  Il n’est pas utilisé à d’autres fins.
- La virgule, `,`, est utilisée pour séparer les éléments d’une séquence. Elle est utilisée pour les littéraux de tuple, les littéraux de tableau, les listes d’arguments, les définitions de tuple et les listes de types. **Dans le cadre d’une modification par rapport aux versions précédentes, `;` n’est plus pris en charge comme séparateur pour les littéraux de tableau.**
- Le deux-points, `:`, est utilisé pour introduire une annotation de type. Il est principalement utilisé dans les signatures appelables.
  Étant donné que le deux points introduit toujours une signature de type, l’opérateur conditionnel ternaire introduit en 0.3 utilise une barre verticale, `|`, pour séparer les valeurs vraies et fausses ; par conséquent, Q# utilise `cond ? tval | fval` au lieu du deux-points comme séparateur, comme en C#.
  
