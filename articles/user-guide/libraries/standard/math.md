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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="46532-103">Fonctions mathématiques classiques</span><span class="sxs-lookup"><span data-stu-id="46532-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="46532-104">Ces fonctions sont principalement utilisées pour travailler avec les Q# types de données intégrés `Int` , `Double` et `Range` .</span><span class="sxs-lookup"><span data-stu-id="46532-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="46532-105">L' <xref:microsoft.quantum.intrinsic.random> opération a une signature `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="46532-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="46532-106">Il prend un tableau de doubles comme entrée et retourne un index sélectionné de façon aléatoire dans le tableau en tant que `Int` .</span><span class="sxs-lookup"><span data-stu-id="46532-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="46532-107">La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index.</span><span class="sxs-lookup"><span data-stu-id="46532-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="46532-108">n éléments de tableau égaux à zéro sont ignorés et leurs index ne sont jamais retournés.</span><span class="sxs-lookup"><span data-stu-id="46532-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="46532-109">Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="46532-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
