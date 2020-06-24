---
title: 'Math dans les bibliothèques standard Q #'
description: 'Découvrez les fonctions mathématiques classiques des bibliothèques standard Q # utilisées avec les types de données intégrés.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274954"
---
# <a name="classical-mathematical-functions"></a>Fonctions mathématiques classiques #

Ces fonctions sont principalement utilisées pour travailler avec les types de données intégrés Q # `Int` , `Double` et `Range` .

L' <xref:microsoft.quantum.intrinsic.random> opération a une signature `(Double[] => Int)` .
Il prend un tableau de doubles comme entrée et retourne un index sélectionné de façon aléatoire dans le tableau en tant que `Int` .
La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index. n éléments de tableau égaux à zéro sont ignorés et leurs index ne sont jamais retournés.
Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.
