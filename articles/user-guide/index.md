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
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231755"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="9eb60-103">Guide de l’utilisateurQ#</span><span class="sxs-lookup"><span data-stu-id="9eb60-103">The Q# User Guide</span></span>

<span data-ttu-id="9eb60-104">Bienvenue dans le Guide de l’utilisateur Q# !</span><span class="sxs-lookup"><span data-stu-id="9eb60-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="9eb60-105">Dans les différentes rubriques de ce guide, nous présentons quelques bases du développement de programmes quantiques avec Q#.</span><span class="sxs-lookup"><span data-stu-id="9eb60-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="9eb60-106">Nous nous référons au [Guide du langage Q#](xref:microsoft.quantum.qsharp.index) pour obtenir une spécification complète et une documentation sur le langage de programmation quantique Q#.</span><span class="sxs-lookup"><span data-stu-id="9eb60-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="9eb60-107">Contenu du Guide de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="9eb60-107">User Guide Contents</span></span>

- <span data-ttu-id="9eb60-108">[Programmes Q#](xref:microsoft.quantum.guide.programs): Présentation rapide des programmes quantiques dans Q#.</span><span class="sxs-lookup"><span data-stu-id="9eb60-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="9eb60-109">[Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs) : explique comment est exécuté un programme Q# et présente les différentes façons d’appeler le programme, à savoir, à partir de la ligne de commande, dans les notebooks Jupyter Q# ou à partir d’un programme hôte classique écrit en Python ou en langage .NET.</span><span class="sxs-lookup"><span data-stu-id="9eb60-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="9eb60-110">[Test et débogage](xref:microsoft.quantum.guide.testingdebugging) : présente en détail certaines techniques vous permettant de vérifier que votre code fait ce qu’il est censé faire.</span><span class="sxs-lookup"><span data-stu-id="9eb60-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="9eb60-111">En raison de l’opacité générale des informations quantiques, le débogage d’un programme quantique peut nécessiter des techniques spécialisées.</span><span class="sxs-lookup"><span data-stu-id="9eb60-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="9eb60-112">Heureusement, Q# prend en charge la plupart des techniques de débogage classiques bien connues des programmeurs en plus de celles spécifiques au domaine quantique.</span><span class="sxs-lookup"><span data-stu-id="9eb60-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="9eb60-113">Citons par exemple la création et l’exécution de tests unitaires dans Q#, l’incorporation d’*assertions* sur des valeurs et des probabilités dans votre code, ainsi que les fonctions `Dump` qui génèrent les états des ordinateurs cibles.</span><span class="sxs-lookup"><span data-stu-id="9eb60-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="9eb60-114">Ces derniers peuvent être utilisés avec notre simulateur d’état complet pour déboguer certaines parties des calculs en contournant des limitations quantiques (par exemple, le théorème d’[impossibilité du clonage](xref:microsoft.quantum.concepts.pauli)).</span><span class="sxs-lookup"><span data-stu-id="9eb60-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="9eb60-115">Simulateurs quantiques et estimateurs de ressources</span><span class="sxs-lookup"><span data-stu-id="9eb60-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="9eb60-116">[Simulateurs quantiques et applications hôtes](xref:microsoft.quantum.machines) : vue d’ensemble des différents simulateurs disponibles et de la manière dont les programmes hôtes et les ordinateurs cibles fonctionnent ensemble pour exécuter les programmes Q#.</span><span class="sxs-lookup"><span data-stu-id="9eb60-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="9eb60-117">[Simulateur d’état complet](xref:microsoft.quantum.machines.full-state-simulator) : ordinateur cible qui simule l’état quantique complet.</span><span class="sxs-lookup"><span data-stu-id="9eb60-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="9eb60-118">Utile pour l’exécution ou le débogage complet de programmes à plus petite échelle (moins de quelques dizaines de qubits)</span><span class="sxs-lookup"><span data-stu-id="9eb60-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="9eb60-119">[Estimateur de ressources](xref:microsoft.quantum.machines.resources-estimator) : estime les ressources nécessaires pour exécuter une instance donnée d’une opération Q# sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="9eb60-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="9eb60-120">[Simulateur de trace](xref:microsoft.quantum.machines.qc-trace-simulator.intro) : exécute un programme quantique sans simuler réellement l’état d’un ordinateur quantique et peut donc exécuter des programmes quantiques qui utilisent des milliers de qubits.</span><span class="sxs-lookup"><span data-stu-id="9eb60-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="9eb60-121">Utile pour le débogage de code classique au sein d’un programme quantique ainsi que pour l’estimation des ressources requises.</span><span class="sxs-lookup"><span data-stu-id="9eb60-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="9eb60-122">[Simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) : simulateur quantique à usage spécifique qui peut être utilisé avec des millions de qubits, mais uniquement pour les programmes avec un ensemble limité d’opérations quantiques (X, CNOT et X multicontrôlées).</span><span class="sxs-lookup"><span data-stu-id="9eb60-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="9eb60-123">Pages de référence rapide</span><span class="sxs-lookup"><span data-stu-id="9eb60-123">Quick Reference Pages</span></span>

- <span data-ttu-id="9eb60-124">[Commandes magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp) : page de référence rapide pour les commandes IQ# magic dans les notebooks Jupyter Q#.</span><span class="sxs-lookup"><span data-stu-id="9eb60-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
