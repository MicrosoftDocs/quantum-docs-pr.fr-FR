---
title: Guide de l’utilisateurQ#
description: Vue d’ensemble de l’objectif et du contenu du Guide de l’utilisateur
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 81f31a531a1b50ead332bb578ccf392ddced9e8d
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771376"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="e2287-103">Guide de l’utilisateurQ#</span><span class="sxs-lookup"><span data-stu-id="e2287-103">The Q# User Guide</span></span>

<span data-ttu-id="e2287-104">Bienvenue dans le Guide de l’utilisateur Q# !</span><span class="sxs-lookup"><span data-stu-id="e2287-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="e2287-105">Dans les différentes rubriques de ce guide, nous allons détailler les concepts de base du langage Q# et toutes les informations dont vous avez besoin pour écrire des programmes quantiques.</span><span class="sxs-lookup"><span data-stu-id="e2287-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="e2287-106">Contenu du Guide de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="e2287-106">User Guide Contents</span></span>

- <span data-ttu-id="e2287-107">[Concepts de base Q#](xref:microsoft.quantum.guide.basics) : présentation de l’objectif et des fonctionnalités du langage de programmation Q#.</span><span class="sxs-lookup"><span data-stu-id="e2287-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="e2287-108">[Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs) : explique comment est exécuté un programme Q# et présente les différentes façons d’appeler le programme, à savoir, à partir de la ligne de commande, dans les notebooks Jupyter Q# ou à partir d’un programme hôte classique écrit en Python ou en langage .NET.</span><span class="sxs-lookup"><span data-stu-id="e2287-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="no-locq-language"></a><span data-ttu-id="e2287-109">Language Q#</span><span class="sxs-lookup"><span data-stu-id="e2287-109">Q# Language</span></span>

- <span data-ttu-id="e2287-110">[Types dans Q#](xref:microsoft.quantum.guide.types) : présente le modèle de type Q# et décrit la syntaxe permettant de spécifier et d’utiliser les types.</span><span class="sxs-lookup"><span data-stu-id="e2287-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="e2287-111">[Expressions de type](xref:microsoft.quantum.guide.expressions) : explique comment spécifier, référencer, combiner et utiliser les valeurs de chaque type en Q#.</span><span class="sxs-lookup"><span data-stu-id="e2287-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-no-locq"></a><span data-ttu-id="e2287-112">Utilisation de Q#</span><span class="sxs-lookup"><span data-stu-id="e2287-112">Using Q#</span></span>

- <span data-ttu-id="e2287-113">[Structure de fichiers Q#](xref:microsoft.quantum.guide.filestructure) : décrit la structure et la syntaxe d’un fichier `*.qs` Q#.</span><span class="sxs-lookup"><span data-stu-id="e2287-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="e2287-114">[Opérations et fonctions](xref:microsoft.quantum.guide.operationsfunctions) détaille les deux types pouvant être appelés du langage Q# : les *opérations* (qui incluent une action sur les registres qubit) et les *fonctions* (qui fonctionnent strictement avec des informations classiques).</span><span class="sxs-lookup"><span data-stu-id="e2287-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="e2287-115">Vous voyez ici comment les définir et les appeler, notamment les versions adjacentes et contrôlées des opérations quantiques.</span><span class="sxs-lookup"><span data-stu-id="e2287-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="e2287-116">[Variables](xref:microsoft.quantum.guide.variables) : décrit le rôle des variables dans les programmes Q# et comment les exploiter efficacement.</span><span class="sxs-lookup"><span data-stu-id="e2287-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="e2287-117">Par exemple, vous pouvez trouver des informations sur les portées de liaison ainsi que la différence entre les variables mutables et non mutables et comment les affecter ou les réaffecter.</span><span class="sxs-lookup"><span data-stu-id="e2287-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="e2287-118">[Utilisation des qubits](xref:microsoft.quantum.guide.qubits) : décrit les fonctionnalités de Q# qui permettent de traiter des qubits individuels et des systèmes de qubits. Plus précisément, vous apprendrez à les allouer, à leur appliquer des opérations et à les mesurer.</span><span class="sxs-lookup"><span data-stu-id="e2287-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="e2287-119">[Flux de contrôle](xref:microsoft.quantum.guide.controlflow) : décrit les modèles de flux de contrôle de programmation disponibles dans Q#, notamment de nombreuses techniques standard (comme le traitement conditionnel, les boucles *for* et les boucles *while*) ainsi que le modèle *Répéter jusqu’à réussir* spécifique au domaine quantique.</span><span class="sxs-lookup"><span data-stu-id="e2287-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional processing, *for* loops, *while* loops) as well as the quantum-specific *Repeat-Until-Success* pattern.</span></span>

- <span data-ttu-id="e2287-120">[Test et débogage](xref:microsoft.quantum.guide.testingdebugging) : présente en détail certaines techniques vous permettant de vérifier que votre code fait ce qu’il est censé faire.</span><span class="sxs-lookup"><span data-stu-id="e2287-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="e2287-121">En raison de l’opacité générale des informations quantiques, le débogage d’un programme quantique peut nécessiter des techniques spécialisées.</span><span class="sxs-lookup"><span data-stu-id="e2287-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="e2287-122">Heureusement, Q# prend en charge la plupart des techniques de débogage classiques bien connues des programmeurs en plus de celles spécifiques au domaine quantique.</span><span class="sxs-lookup"><span data-stu-id="e2287-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="e2287-123">Citons par exemple la création et l’exécution de tests unitaires dans Q#, l’incorporation d’*assertions* sur des valeurs et des probabilités dans votre code, ainsi que les fonctions `Dump` qui génèrent les états des ordinateurs cibles.</span><span class="sxs-lookup"><span data-stu-id="e2287-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="e2287-124">Ces derniers peuvent être utilisés avec notre simulateur d’état complet pour déboguer certaines parties des calculs en contournant des limitations quantiques (par exemple, le théorème d’[impossibilité du clonage](xref:microsoft.quantum.concepts.pauli)).</span><span class="sxs-lookup"><span data-stu-id="e2287-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="e2287-125">Simulateurs quantiques et estimateurs de ressources</span><span class="sxs-lookup"><span data-stu-id="e2287-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="e2287-126">[Simulateurs quantiques et applications hôtes](xref:microsoft.quantum.machines) : vue d’ensemble des différents simulateurs disponibles et de la manière dont les programmes hôtes et les ordinateurs cibles fonctionnent ensemble pour exécuter les programmes Q#.</span><span class="sxs-lookup"><span data-stu-id="e2287-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="e2287-127">[Simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) : ordinateur cible qui simule l’état quantique complet.</span><span class="sxs-lookup"><span data-stu-id="e2287-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="e2287-128">Utile pour l’exécution ou le débogage complet de programmes à plus petite échelle (moins de quelques dizaines de qubits)</span><span class="sxs-lookup"><span data-stu-id="e2287-128">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="e2287-129">[Estimateur de ressources](xref:microsoft.quantum.machines.resources-estimator) : estime les ressources nécessaires pour exécuter une instance donnée d’une opération Q# sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="e2287-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="e2287-130">[Simulateur de trace](xref:microsoft.quantum.machines.qc-trace-simulator.intro) : exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique et peut donc exécuter des programmes quantiques qui utilisent des milliers de qubits.</span><span class="sxs-lookup"><span data-stu-id="e2287-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="e2287-131">Utile pour le débogage de code classique au sein d’un programme quantique ainsi que pour l’estimation des ressources requises.</span><span class="sxs-lookup"><span data-stu-id="e2287-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="e2287-132">[Simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) : simulateur quantique à usage spécifique qui peut être utilisé avec des millions de qubits, mais uniquement pour les programmes avec un ensemble limité d’opérations quantiques (X, CNOT et X multicontrôlées).</span><span class="sxs-lookup"><span data-stu-id="e2287-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="e2287-133">Pages de référence rapide</span><span class="sxs-lookup"><span data-stu-id="e2287-133">Quick Reference Pages</span></span>

- <span data-ttu-id="e2287-134">[Commandes magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp) : page de référence rapide pour les commandes IQ# magic dans les notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="e2287-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
