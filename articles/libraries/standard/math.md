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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="8e3aa-103">Fonctions mathématiques classiques</span><span class="sxs-lookup"><span data-stu-id="8e3aa-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="8e3aa-104">Ces fonctions sont principalement utilisées pour travailler avec les types de données intégrés Q # `Int`, `Double`et `Range`.</span><span class="sxs-lookup"><span data-stu-id="8e3aa-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="8e3aa-105">L’opération de <xref:microsoft.quantum.intrinsic.random> a des `(Double[] => Int)`de signature.</span><span class="sxs-lookup"><span data-stu-id="8e3aa-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="8e3aa-106">Il prend un tableau de doubles comme entrée et retourne un index sélectionné de façon aléatoire dans le tableau en tant que `Int`.</span><span class="sxs-lookup"><span data-stu-id="8e3aa-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="8e3aa-107">La probabilité de sélectionner un index spécifique est proportionnelle à la valeur de l’élément de tableau au niveau de cet index.</span><span class="sxs-lookup"><span data-stu-id="8e3aa-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="8e3aa-108">n éléments de tableau égaux à zéro sont ignorés et leurs index ne sont jamais retournés.</span><span class="sxs-lookup"><span data-stu-id="8e3aa-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="8e3aa-109">Si un élément de tableau est inférieur à zéro, ou si aucun élément de tableau n’est supérieur à zéro, l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="8e3aa-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>