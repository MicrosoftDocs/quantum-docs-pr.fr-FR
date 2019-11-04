---
title: Le langage de programmation Q# | Microsoft Docs
description: Le langage de programmation Q#
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: 560926f6f3e05c32a935f01ca5107a614e743ee2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442472"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="01b99-103">Le langage de programmation Q#</span><span class="sxs-lookup"><span data-stu-id="01b99-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="01b99-104">Introduction</span><span class="sxs-lookup"><span data-stu-id="01b99-104">Introduction</span></span>

<span data-ttu-id="01b99-105">Un modèle naturel de calcul quantique consiste à traiter l’ordinateur quantique comme un coprocesseur, semblable à celui utilisé pour les GPU, les FPGA et autres processeurs auxiliaires.</span><span class="sxs-lookup"><span data-stu-id="01b99-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="01b99-106">La logique de commande primaire exécute le code classique sur un ordinateur « hôte » classique.</span><span class="sxs-lookup"><span data-stu-id="01b99-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="01b99-107">Le cas échéant, le programme hôte peut invoquer un sous-programme qui s’exécute sur le processeur auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="01b99-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="01b99-108">À la fin du sous-programme, le programme hôte obtient l’accès aux résultats du sous-programme.</span><span class="sxs-lookup"><span data-stu-id="01b99-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="01b99-109">Q# (Q-sharp) est un langage de programmation spécifique au domaine utilisé pour exprimer les algorithmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="01b99-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="01b99-110">Il doit être utilisé pour écrire des sous-programmes qui s’exécutent sur un processeur quantique auxiliaire, sous le contrôle d’un ordinateur et d’un programme hôte classiques.</span><span class="sxs-lookup"><span data-stu-id="01b99-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="01b99-111">Tant que les processeurs quantiques ne sont pas largement disponibles, les sous-programmes Q# s’exécutent sur un simulateur.</span><span class="sxs-lookup"><span data-stu-id="01b99-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="01b99-112">Q# fournit un petit ensemble de types primitifs, ainsi que deux méthodes (tableaux et tuples) pour créer de nouveaux types structurés.</span><span class="sxs-lookup"><span data-stu-id="01b99-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="01b99-113">Il prend en charge un modèle procédural de base pour l’écriture de programmes, avec des boucles et des instructions IF/THEN.</span><span class="sxs-lookup"><span data-stu-id="01b99-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="01b99-114">Les constructions de niveau supérieur en Q# sont des types, des opérations et des fonctions définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="01b99-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="01b99-115">Les sections suivantes décrivent en détail :</span><span class="sxs-lookup"><span data-stu-id="01b99-115">The following sections detail:</span></span>
- [<span data-ttu-id="01b99-116">Modèle de type</span><span class="sxs-lookup"><span data-stu-id="01b99-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="01b99-117">Expressions</span><span class="sxs-lookup"><span data-stu-id="01b99-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="01b99-118">Instructions</span><span class="sxs-lookup"><span data-stu-id="01b99-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="01b99-119">Structure de fichiers</span><span class="sxs-lookup"><span data-stu-id="01b99-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="01b99-120">Conventions</span><span class="sxs-lookup"><span data-stu-id="01b99-120">Conventions</span></span>

<span data-ttu-id="01b99-121">Nous veillons à ce que des signes de ponctuation communs soient utilisés de façon uniforme dans toutes les situations.</span><span class="sxs-lookup"><span data-stu-id="01b99-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="01b99-122">Nous pensons que cela rendra Q# plus facile à apprendre et à lire, car ces marques signifient toujours la même chose et le même concept est toujours représenté de la même façon.</span><span class="sxs-lookup"><span data-stu-id="01b99-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="01b99-123">Plus précisément :</span><span class="sxs-lookup"><span data-stu-id="01b99-123">Specifically:</span></span>

- <span data-ttu-id="01b99-124">Le point-virgule, `;`, est utilisé pour terminer une instruction ou une directive à une ligne.</span><span class="sxs-lookup"><span data-stu-id="01b99-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="01b99-125">Il n’est pas utilisé à d’autres fins.</span><span class="sxs-lookup"><span data-stu-id="01b99-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="01b99-126">La virgule, `,`, est utilisée pour séparer les éléments d’une séquence.</span><span class="sxs-lookup"><span data-stu-id="01b99-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="01b99-127">Elle est utilisée pour les littéraux de tuple, les littéraux de tableau, les listes d’arguments, les définitions de tuple et les listes de types.</span><span class="sxs-lookup"><span data-stu-id="01b99-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="01b99-128">**Dans le cadre d’une modification par rapport aux versions précédentes, `;` n’est plus pris en charge comme séparateur pour les littéraux de tableau.**</span><span class="sxs-lookup"><span data-stu-id="01b99-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="01b99-129">Le deux-points, `:`, est utilisé pour introduire une annotation de type.</span><span class="sxs-lookup"><span data-stu-id="01b99-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="01b99-130">Il est principalement utilisé dans les signatures appelables.</span><span class="sxs-lookup"><span data-stu-id="01b99-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="01b99-131">Étant donné que le deux points introduit toujours une signature de type, l’opérateur conditionnel ternaire introduit en 0.3 utilise une barre verticale, `|`, pour séparer les valeurs vraies et fausses ; par conséquent, Q# utilise `cond ? tval | fval` au lieu du deux-points comme séparateur, comme en C#.</span><span class="sxs-lookup"><span data-stu-id="01b99-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
