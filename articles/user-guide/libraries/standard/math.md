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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="f8161-103">Fonctions mathématiques classiques</span><span class="sxs-lookup"><span data-stu-id="f8161-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="f8161-104">Ces fonctions sont principalement utilisées pour travailler avec les types de données intégrés Q # `Int` , `Double` et `Range` .</span><span class="sxs-lookup"><span data-stu-id="f8161-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="f8161-105">L' <xref:microsoft.quantum.intrinsic.random> opération a une signature `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="f8161-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="f8161-106">Il prend un tableau de doubles comme entrée et retourne un index sélectionné de façon aléatoire dans le tableau en tant que `Int` .</span><span class="sxs-lookup"><span data-stu-id="f8161-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="f8161-107">La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index.</span><span class="sxs-lookup"><span data-stu-id="f8161-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="f8161-108">n éléments de tableau égaux à zéro sont ignorés et leurs index ne sont jamais retournés.</span><span class="sxs-lookup"><span data-stu-id="f8161-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="f8161-109">Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="f8161-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
