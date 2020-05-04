---
title: Découvrir comment installer le Microsoft Quantum Development Kit (QDK)
description: Découvrez comment installer le kit de développement Microsoft Quantum pour les environnements C#, Python et Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680196"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="9928f-103">Installer le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="9928f-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="9928f-104">Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="9928f-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="9928f-105">Le QDK se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="9928f-105">The QDK consists of:</span></span>

- <span data-ttu-id="9928f-106">le langage de programmation Q#</span><span class="sxs-lookup"><span data-stu-id="9928f-106">the Q# programming language</span></span>
- <span data-ttu-id="9928f-107">un ensemble de bibliothèques qui ont abstrait des fonctionnalités complexes en Q#</span><span class="sxs-lookup"><span data-stu-id="9928f-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="9928f-108">API pour Python et les langages .NET (C#, F# et VB.NET) pour exécuter des programmes quantiques écrits en Q#</span><span class="sxs-lookup"><span data-stu-id="9928f-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="9928f-109">des outils pour faciliter votre développement</span><span class="sxs-lookup"><span data-stu-id="9928f-109">tools to facilitate your development</span></span>

<span data-ttu-id="9928f-110">Les programmes Q# sont souvent associés à un programme hôte écrit dans un langage .NET (en général C#) ou Python.</span><span class="sxs-lookup"><span data-stu-id="9928f-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="9928f-111">Cela nous permet d’appeler des opérations quantiques à partir d’un programme classique.</span><span class="sxs-lookup"><span data-stu-id="9928f-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="9928f-112">QDK fournit également la prise en charge de Q# pour Jupyter Notebook avec le noyau Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="9928f-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="9928f-113">Le QDK est disponible pour plusieurs environnements de développement.</span><span class="sxs-lookup"><span data-stu-id="9928f-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="9928f-114">Sélectionnez votre configuration préférée dans les sections ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="9928f-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="9928f-115">[Application en ligne de commande Q#](xref:microsoft.quantum.install.standalone) : choisissez cette approche si vous souhaitez utiliser Q# à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="9928f-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="9928f-116">Vous n’avez pas besoin d’un pilote ni d’un programme hôte comme avec les options ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9928f-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="9928f-117">[Installer Q# pour Jupyter Notebook](xref:microsoft.quantum.install.jupyter) : choisissez cet environnement pour exécuter du code Q# dans des cellules avec du texte incorporé ou créer des tutoriels interactifs sur l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="9928f-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="9928f-118">[Développer avec Q# et Python](xref:microsoft.quantum.install.python) : si vous souhaitez combiner Python et Q# pour créer un programme hôte Python qui appelle des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="9928f-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="9928f-119">[Développer avec Q# et C# ou F#](xref:microsoft.quantum.install.cs) : si vous souhaitez combiner C# ou F# et Q# pour créer un programme hôte .NET qui appelle des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="9928f-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
