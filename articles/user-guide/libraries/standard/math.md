---
title: Math dans les Q# bibliothèques standard
description: Découvrez les fonctions mathématiques classiques des Q# bibliothèques standard utilisées avec les types de données intégrés.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868421"
---
# <a name="classical-mathematical-functions"></a>Fonctions mathématiques classiques #

Ces fonctions sont principalement utilisées pour travailler avec les Q# types de données intégrés `Int` , `Double` et `Range` .

L' <xref:microsoft.quantum.intrinsic.random> opération a une signature `(Double[] => Int)` .
Il prend un tableau de doubles comme entrée et retourne un index sélectionné de façon aléatoire dans le tableau en tant que `Int` .
La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index. n éléments de tableau égaux à zéro sont ignorés et leurs index ne sont jamais retournés.
Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.
