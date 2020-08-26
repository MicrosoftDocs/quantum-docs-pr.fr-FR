---
title: Installer le Microsoft Quantum Development Kit (QDK)
description: Guide pratique pour installer le Microsoft Quantum Development Kit pour différents environnements.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863706"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c0d5a-103">Installer le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="c0d5a-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c0d5a-104">Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="c0d5a-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="c0d5a-105">Le QDK se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c0d5a-105">The QDK consists of:</span></span>

- <span data-ttu-id="c0d5a-106">Langage de programmation Q#</span><span class="sxs-lookup"><span data-stu-id="c0d5a-106">The Q# programming language</span></span>
- <span data-ttu-id="c0d5a-107">Ensemble de bibliothèques qui résument des fonctionnalités complexes en Q#</span><span class="sxs-lookup"><span data-stu-id="c0d5a-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="c0d5a-108">API pour Python et les langages .NET (C#, F# et VB.NET) pour exécuter des programmes quantiques écrits en Q#</span><span class="sxs-lookup"><span data-stu-id="c0d5a-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="c0d5a-109">Outils pour faciliter votre développement</span><span class="sxs-lookup"><span data-stu-id="c0d5a-109">Tools to facilitate your development</span></span>

<span data-ttu-id="c0d5a-110">Les programmes Q# peuvent être exécutés en tant qu’applications autonomes à l’aide de Visual Studio Code ou Visual Studio, ou via des notebooks Jupyter avec le noyau Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="c0d5a-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="c0d5a-111">Ils peuvent également être associés à un programme hôte écrit dans un langage .NET (généralement C#) ou Python, ce qui vous permet d’appeler des opérations quantiques à partir d’un programme classique.</span><span class="sxs-lookup"><span data-stu-id="c0d5a-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="c0d5a-112">Le workflow de chacune de ces configurations est décrit et comparé aux autres dans [Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="c0d5a-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="c0d5a-113">Pour procéder à l’installation du QDK et à la création de projets Q#, sélectionnez votre configuration préférée :</span><span class="sxs-lookup"><span data-stu-id="c0d5a-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="c0d5a-114">[Développer avec des Q#applications](xref:microsoft.quantum.install.standalone) : choisissez cette approche pour utiliser Q# à partir de l’invite de commande.</span><span class="sxs-lookup"><span data-stu-id="c0d5a-114">[Develop with Q# applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command prompt.</span></span> <span data-ttu-id="c0d5a-115">Vous n’avez pas besoin d’un pilote ni d’un programme hôte comme avec les options ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c0d5a-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="c0d5a-116">[Développer avec des notebooks Jupyter Q#](xref:microsoft.quantum.install.jupyter) : choisissez cet environnement pour exécuter du code Q# dans des cellules avec du texte incorporé ou créer des tutoriels interactifs sur l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="c0d5a-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="c0d5a-117">[Développer avec Q# et Python](xref:microsoft.quantum.install.python) : cette option vous permet de combiner Python et Q# afin de créer un programme hôte Python qui appelle des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="c0d5a-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="c0d5a-118">[Développer avec Q# et .NET](xref:microsoft.quantum.install.cs) : combinez C#, F# ou VB.NET avec Q# pour créer un programme hôte .NET qui appelle des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="c0d5a-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
