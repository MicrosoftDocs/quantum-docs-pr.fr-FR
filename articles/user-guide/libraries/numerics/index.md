---
title: Introduction à la bibliothèque de valeurs numériques de quantum | Microsoft Docs
description: Introduction à la bibliothèque de valeurs numériques de quantum
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273642"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="3e207-103">Introduction à la bibliothèque de valeurs numériques de quantum</span><span class="sxs-lookup"><span data-stu-id="3e207-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="3e207-104">De nombreux algorithmes de quantum reposent sur [oracles](xref:microsoft.quantum.concepts.oracles) qui évaluent les fonctions mathématiques sur une superposition d’entrées.</span><span class="sxs-lookup"><span data-stu-id="3e207-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="3e207-105">Le composant principal de l’algorithme de Shori, par exemple, évalue $f(x) = a^x\operatorname{mod} N$ pour un $a$ fixe, le nombre à factoriser $N$ et $x$ a entier $2n$-qubit dans une superposition uniforme sur toutes les chaînes de $2n$ bits.</span><span class="sxs-lookup"><span data-stu-id="3e207-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="3e207-106">Pour exécuter l’algorithme de Shori sur un ordinateur de quantum réel, cette fonction doit être écrite en termes d’opérations natives de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="3e207-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="3e207-107">À l’aide de la représentation binaire de $x$ avec $x_i $ désignant le $i$-ème compte de bits du bit le moins significatif, $f(x)$ peut être écrit comme $f(x) = a^{\sum_{i = 0}^{2n-1}x_i 2^i} \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="3e207-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="3e207-108">À son tour, ce peut être écrit en tant que produit (mod N) des termes $a^{2^i x_i} = (a^{2^i})^{x_i}$.</span><span class="sxs-lookup"><span data-stu-id="3e207-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="3e207-109">La fonction $f(x)$ peut donc être implémentée à l’aide d’une séquence de démultiplications de $2n$ (modulaires) par $a^{2^i}$ conditionnel sur $x_i$ étant différent de zéro.</span><span class="sxs-lookup"><span data-stu-id="3e207-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="3e207-110">Les constantes $a^{2^i}$ peuvent être précalculées et réduites sur le modulo N avant d’exécuter l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="3e207-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="3e207-111">Cette séquence de multiplications modulaires contrôlées peut être ultérieurement simplifiée : Chaque multiplication peut être effectuée à l’aide d’une séquence d’ajouts modulaires contrôlés par $n$ ; chaque ajout modulaire peut être créé à partir d’un ajout régulier et d’un comparateur.</span><span class="sxs-lookup"><span data-stu-id="3e207-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="3e207-112">Étant donné qu’un grand nombre d’étapes sont nécessaires pour arriver à une implémentation réelle, il serait extrêmement utile d’avoir de telles fonctionnalités disponibles dès le début.</span><span class="sxs-lookup"><span data-stu-id="3e207-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="3e207-113">C’est pourquoi le Quantum Development kit prend en charge un large éventail de fonctionnalités numériques.</span><span class="sxs-lookup"><span data-stu-id="3e207-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="3e207-114">Fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="3e207-114">Functionality</span></span>

<span data-ttu-id="3e207-115">Outre les opérations arithmétiques sur les entiers mentionnées jusqu’à présent, la bibliothèque numérique fournit</span><span class="sxs-lookup"><span data-stu-id="3e207-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

 - <span data-ttu-id="3e207-116">Fonctionnalité entière (non)signée (multiplier, carré, division avec le reste, inversion,...) avec un ou deux nombres entiers de quantum comme entrée</span><span class="sxs-lookup"><span data-stu-id="3e207-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
 - <span data-ttu-id="3e207-117">Fonctionnalité à point fixe (ajouter/soustraire, multiplier, carré, 1/x, évaluation polynomiale) avec un ou deux nombres à point fixe de quantum comme entrée</span><span class="sxs-lookup"><span data-stu-id="3e207-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="3e207-118">Prise en main</span><span class="sxs-lookup"><span data-stu-id="3e207-118">Getting started</span></span>

<span data-ttu-id="3e207-119">Pour commencer à utiliser la bibliothèque de valeurs numériques, extrayez le [guide d’installation](xref:microsoft.quantum.numerics.installation) et plus d’informations sur [l’utilisation de la bibliothèque de valeurs](xref:microsoft.quantum.numerics.usage).</span><span class="sxs-lookup"><span data-stu-id="3e207-119">To get started with the Numerics Library, check out the [installation guide](xref:microsoft.quantum.numerics.installation) and more information on [using the Numerics Library](xref:microsoft.quantum.numerics.usage).</span></span>
