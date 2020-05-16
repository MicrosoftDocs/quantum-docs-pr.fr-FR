---
title: Commandes magiques IQ#
description: 'Page de référence rapide pour les commandes Magic # Magic avec des blocs-notes Jupyter Q #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431017"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="74687-103">Commandes magiques IQ#</span><span class="sxs-lookup"><span data-stu-id="74687-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="74687-104">Général</span><span class="sxs-lookup"><span data-stu-id="74687-104">General</span></span>

- <span data-ttu-id="74687-105">`%config`: Définit ou obtient des préférences de configuration.</span><span class="sxs-lookup"><span data-stu-id="74687-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="74687-106">`%estimate`: Exécute une fonction ou une opération donnée sur l’ordinateur cible QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="74687-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="74687-107">`%lsmagic`: Retourne une liste de toutes les commandes Magic actuellement disponibles.</span><span class="sxs-lookup"><span data-stu-id="74687-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="74687-108">`%package`: Permet de charger un package NuGet.</span><span class="sxs-lookup"><span data-stu-id="74687-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="74687-109">`%performance`: Signale les métriques de performances actuelles pour ce noyau.</span><span class="sxs-lookup"><span data-stu-id="74687-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="74687-110">`%simulate`: Exécute une fonction ou une opération donnée sur l’ordinateur cible QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="74687-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="74687-111">`%toffoli`: Exécute une fonction ou une opération donnée sur l’ordinateur cible du simulateur ToffoliSimulator.</span><span class="sxs-lookup"><span data-stu-id="74687-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="74687-112">`%who`: Fournit des actions liées à l’espace de travail actuel.</span><span class="sxs-lookup"><span data-stu-id="74687-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="74687-113">`%workspace`: Retourne une liste de toutes les opérations et fonctions définies dans la session active, de manière interactive ou chargée à partir de l’espace de travail actuel.</span><span class="sxs-lookup"><span data-stu-id="74687-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="74687-114">Chimique</span><span class="sxs-lookup"><span data-stu-id="74687-114">Chemistry</span></span>

- <span data-ttu-id="74687-115">`%chemistry.broombridge`: Charge et retourne la représentation du problème de structure électronique Broombridge à partir d’un fichier. YAML donné.</span><span class="sxs-lookup"><span data-stu-id="74687-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="74687-116">`%chemistry.encode`: Encode un fermion Hamilton dans un format utilisable par Q #.</span><span class="sxs-lookup"><span data-stu-id="74687-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="74687-117">`%chemistry.fh.add_terms`: Ajoute des termes à un fermion Hamilton.</span><span class="sxs-lookup"><span data-stu-id="74687-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="74687-118">`%chemistry.fh.load`: Charge le fermion Hamilton pour un problème de structure électronique.</span><span class="sxs-lookup"><span data-stu-id="74687-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="74687-119">Le problème est chargé à partir d’un fichier ou passé comme argument.</span><span class="sxs-lookup"><span data-stu-id="74687-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="74687-120">`%chemistry.inputstate.load`: Charge le problème de structure électronique Broombridge et retourne l’état d’entrée sélectionné.</span><span class="sxs-lookup"><span data-stu-id="74687-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="74687-121">À partir du package Microsoft. Quantum. katas</span><span class="sxs-lookup"><span data-stu-id="74687-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="74687-122">`%kata`: Exécute un seul test et signale si le test a réussi.</span><span class="sxs-lookup"><span data-stu-id="74687-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="74687-123">`%check_kata`: Vérifie l’implémentation de référence pour un test de Kata unique.</span><span class="sxs-lookup"><span data-stu-id="74687-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="74687-124">En particulier, il substitue l’implémentation de référence pour une tâche unique dans la cellule et signale si le test a réussi.</span><span class="sxs-lookup"><span data-stu-id="74687-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
