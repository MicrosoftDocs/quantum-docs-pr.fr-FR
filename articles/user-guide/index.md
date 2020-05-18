---
title: Guide de l’utilisateur Q#
description: Vue d’ensemble de l’objectif et du contenu du Guide de l’utilisateur
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430609"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="8d97f-103">Guide de l’utilisateur Q#</span><span class="sxs-lookup"><span data-stu-id="8d97f-103">The Q# User Guide</span></span>

<span data-ttu-id="8d97f-104">Bienvenue dans le Guide de l’utilisateur Q# !</span><span class="sxs-lookup"><span data-stu-id="8d97f-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="8d97f-105">Nous allons ici détailler les concepts de base du langage Q# et toutes les informations dont vous avez besoin pour écrire des programmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="8d97f-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="8d97f-106">Contenu du Guide de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="8d97f-106">User Guide Contents</span></span>

- <span data-ttu-id="8d97f-107">[Concepts Q# de base](xref:microsoft.quantum.guide.basics) : vue d’ensemble d’introduction de l’objectif et des fonctionnalités du langage de programmation Q#.</span><span class="sxs-lookup"><span data-stu-id="8d97f-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="8d97f-108">Langage Q#</span><span class="sxs-lookup"><span data-stu-id="8d97f-108">Q# Language</span></span>

- <span data-ttu-id="8d97f-109">[Types en Q#](xref:microsoft.quantum.guide.types) : présente le modèle de type Q# et décrit la syntaxe permettant de spécifier et d’utiliser les types.</span><span class="sxs-lookup"><span data-stu-id="8d97f-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="8d97f-110">[Expressions du type](xref:microsoft.quantum.guide.expressions) : explique comment spécifier, référencer, combiner et utiliser les valeurs de chaque type en Q#.</span><span class="sxs-lookup"><span data-stu-id="8d97f-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="8d97f-111">Utilisation de Q#</span><span class="sxs-lookup"><span data-stu-id="8d97f-111">Using Q#</span></span>

- <span data-ttu-id="8d97f-112">[Structure de fichiers Q#](xref:microsoft.quantum.guide.filestructure) : décrit la structure et la syntaxe d’un fichier `*.qs` Q#.</span><span class="sxs-lookup"><span data-stu-id="8d97f-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="8d97f-113">[Opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions) : détaille les deux types pouvant être appelés du langage Q# : les *opérations* (qui incluent une action sur les registres qubit) et les *fonctions* (qui fonctionnent strictement avec des informations classiques).</span><span class="sxs-lookup"><span data-stu-id="8d97f-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="8d97f-114">Vous voyez ici comment les définir et les appeler, notamment les versions adjacentes et contrôlées des opérations quantiques.</span><span class="sxs-lookup"><span data-stu-id="8d97f-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="8d97f-115">[Variables](xref:microsoft.quantum.guide.variables) : décrit le rôle des variables dans les programmes Q# et comment les exploiter efficacement.</span><span class="sxs-lookup"><span data-stu-id="8d97f-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="8d97f-116">Par exemple, vous pouvez trouver des informations sur les portées de liaison ainsi que la différence entre les variables mutables/immuables et comment les assigner/réassigner.</span><span class="sxs-lookup"><span data-stu-id="8d97f-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="8d97f-117">[Utilisation des qubits](xref:microsoft.quantum.guide.qubits) : décrit les fonctionnalités de Q# qui permettent de traiter des qubits individuels et des systèmes de qubits.</span><span class="sxs-lookup"><span data-stu-id="8d97f-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="8d97f-118">Plus précisément, vous apprendrez à les allouer, à leur appliquer des opérations et finalement à les mesurer.</span><span class="sxs-lookup"><span data-stu-id="8d97f-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="8d97f-119">[Flux de contrôle](xref:microsoft.quantum.guide.controlflow) : décrit les modèles de flux de contrôle de programmation disponibles dans Q#, notamment de nombreuses techniques standard (exécution conditionnelle, boucles for, boucles while, etc.) ainsi que le modèle « répéter-jusqu’à-réussite » spécifique au domaine quantique.</span><span class="sxs-lookup"><span data-stu-id="8d97f-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="8d97f-120">[Tests et débogage](xref:microsoft.quantum.guide.testingdebugging) : présente en détail certaines techniques vous permettant de vérifier que votre code fait ce qu’il est censé faire.</span><span class="sxs-lookup"><span data-stu-id="8d97f-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="8d97f-121">En raison de l’opacité générale des informations quantiques, le débogage d’un programme quantique peut nécessiter des techniques spécialisées.</span><span class="sxs-lookup"><span data-stu-id="8d97f-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="8d97f-122">Heureusement, Q# prend en charge la plupart des techniques de débogage classiques bien connues des programmeurs en plus de celles spécifiques au domaine quantique.</span><span class="sxs-lookup"><span data-stu-id="8d97f-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="8d97f-123">Citons par exemple la création et l’exécution de tests unitaires dans Q#, l’incorporation d’*assertions* sur des valeurs et des probabilités dans votre code, ainsi que les fonctions `Dump` qui génèrent l’état de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="8d97f-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="8d97f-124">Ce dernier peut être utilisé avec notre simulateur d’état complet pour déboguer certaines parties des calculs en contournant des limitations quantiques (par exemple, le théorème d’impossibilité du clonage).</span><span class="sxs-lookup"><span data-stu-id="8d97f-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="8d97f-125">Simulateurs quantiques et estimateurs de ressources</span><span class="sxs-lookup"><span data-stu-id="8d97f-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="8d97f-126">[Simulateurs quantiques et applications hôtes](xref:microsoft.quantum.machines) : vue d’ensemble des différents simulateurs disponibles avec le modèle d’exécution générale entre le programme hôte et les ordinateurs cibles.</span><span class="sxs-lookup"><span data-stu-id="8d97f-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="8d97f-127">[Simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) : ordinateur cible qui simule l’état quantique complet.</span><span class="sxs-lookup"><span data-stu-id="8d97f-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="8d97f-128">Utile pour l’exécution ou le débogage complet de programmes à plus petite échelle (moins de quelques douzaines de qubits)</span><span class="sxs-lookup"><span data-stu-id="8d97f-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="8d97f-129">[Estimateur de ressources](xref:microsoft.quantum.machines.resources-estimator) : estime les ressources nécessaires pour exécuter une instance donnée d’une opération Q# sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="8d97f-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="8d97f-130">[Simulateur de trace](xref:microsoft.quantum.machines.qc-trace-simulator.intro) : exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique et peut par conséquent exécuter des programmes quantiques qui utilisent des milliers de qubits.</span><span class="sxs-lookup"><span data-stu-id="8d97f-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="8d97f-131">Utile pour le débogage de code classique au sein d’un programme quantique ainsi que pour l’estimation des ressources requises.</span><span class="sxs-lookup"><span data-stu-id="8d97f-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="8d97f-132">[Simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) : simulateur quantique à usage spécifique qui peut être utilisé avec des millions de qubits, mais uniquement pour les programmes avec un ensemble limité d’opérations quantiques (à savoir X, CNOT et X multicontrôlées).</span><span class="sxs-lookup"><span data-stu-id="8d97f-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="8d97f-133">Pages de référence rapide</span><span class="sxs-lookup"><span data-stu-id="8d97f-133">Quick Reference Pages</span></span>

- <span data-ttu-id="8d97f-134">[Commandes IQ# Magic](xref:microsoft.quantum.guide.quickref.iqsharp) : page de référence rapide pour les commandes IQ# Magic dans les notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="8d97f-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
