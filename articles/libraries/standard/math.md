---
title: 'Q # bibliothèques standard-Math | Microsoft Docs'
description: 'Bibliothèques standard Q #-Math'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184455"
---
# <a name="classical-mathematical-functions"></a>Fonctions mathématiques classiques #

Ces fonctions sont principalement utilisées pour travailler avec les types de données intégrés Q # `Int`, `Double`et `Range`.

L’opération de <xref:microsoft.quantum.intrinsic.random> a des `(Double[] => Int)`de signature.
Il prend un tableau de doubles comme entrée et retourne un index sélectionné de façon aléatoire dans le tableau en tant que `Int`.
La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index. n éléments de tableau égaux à zéro sont ignorés et leurs index ne sont jamais retournés.
Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.