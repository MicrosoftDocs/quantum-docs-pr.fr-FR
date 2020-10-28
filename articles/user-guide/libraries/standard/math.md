---
title: 'Math dans les :::no-loc(Q#)::: bibliothèques standard'
description: 'Découvrez les fonctions mathématiques classiques des :::no-loc(Q#)::: bibliothèques standard utilisées avec les types de données intégrés.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692055"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="598f6-103">Fonctions mathématiques classiques</span><span class="sxs-lookup"><span data-stu-id="598f6-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="598f6-104">Ces fonctions sont principalement utilisées pour travailler avec les :::no-loc(Q#)::: types de données intégrés `Int` , `Double` et `Range` .</span><span class="sxs-lookup"><span data-stu-id="598f6-104">These functions are primarily used to work with the :::no-loc(Q#)::: built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="598f6-105">L' <xref:Microsoft.Quantum.Intrinsic.Random> opération a une signature `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="598f6-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="598f6-106">Il prend un tableau de doubles comme entrée et retourne un index sélectionné de façon aléatoire dans le tableau en tant que `Int` .</span><span class="sxs-lookup"><span data-stu-id="598f6-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="598f6-107">La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index.</span><span class="sxs-lookup"><span data-stu-id="598f6-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="598f6-108">n éléments de tableau égaux à zéro sont ignorés et leurs index ne sont jamais retournés.</span><span class="sxs-lookup"><span data-stu-id="598f6-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="598f6-109">Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="598f6-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
