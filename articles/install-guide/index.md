---
title: Découvrir comment installer le Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 0e9dd1c74316eeb1fa7bbbf657d2e78231ee4294
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036506"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="74e01-102">Installer le Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="74e01-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="74e01-103">Découvrez comment installer le Microsoft Quantum Development Kit (QDK) afin de pouvoir vous lancer dans la programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="74e01-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="74e01-104">Le QDK se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="74e01-104">The QDK consists of:</span></span>

- <span data-ttu-id="74e01-105">le langage de programmation Q#</span><span class="sxs-lookup"><span data-stu-id="74e01-105">the Q# programming language</span></span>
- <span data-ttu-id="74e01-106">un ensemble de bibliothèques qui ont abstrait des fonctionnalités complexes en Q#</span><span class="sxs-lookup"><span data-stu-id="74e01-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="74e01-107">API pour Python et les langages .NET (C#, F# et VB.NET) pour exécuter des programmes quantiques écrits en Q#</span><span class="sxs-lookup"><span data-stu-id="74e01-107">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="74e01-108">des outils pour faciliter votre développement</span><span class="sxs-lookup"><span data-stu-id="74e01-108">tools to facilitate your development</span></span>

<span data-ttu-id="74e01-109">Les programmes Q# sont souvent associés à un programme hôte écrit dans un langage .NET (en général C#) ou Python.</span><span class="sxs-lookup"><span data-stu-id="74e01-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="74e01-110">Cela nous permet d’appeler des opérations quantiques à partir d’un programme classique.</span><span class="sxs-lookup"><span data-stu-id="74e01-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="74e01-111">QDK fournit également la prise en charge de Q# pour Jupyter Notebook avec le noyau Jupyter IQ#.</span><span class="sxs-lookup"><span data-stu-id="74e01-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="74e01-112">Le QDK est disponible pour plusieurs environnements de développement.</span><span class="sxs-lookup"><span data-stu-id="74e01-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="74e01-113">Sélectionnez votre configuration préférée dans les sections ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="74e01-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="74e01-114">[Installer Q# pour C#](xref:microsoft.quantum.install.cs) : choisissez cet environnement si vous souhaitez combiner C# et Q# pour créer un programme hôte en C# qui appelle des opérations en Q#.</span><span class="sxs-lookup"><span data-stu-id="74e01-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="74e01-115">[Installer Q# pour Python](xref:microsoft.quantum.install.python) : choisissez cet environnement si vous souhaitez combiner Python et Q# pour créer un programme hôte en Python qui appelle des opérations en Q#.</span><span class="sxs-lookup"><span data-stu-id="74e01-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="74e01-116">[Installer Q# pour Jupyter Notebook](xref:microsoft.quantum.install.jupyter) : choisissez cet environnement pour exécuter du code Q# dans des cellules avec du texte incorporé ou créer des tutoriels interactifs sur l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="74e01-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="74e01-117">Ne choisissez pas cet environnement si vous souhaitez combiner Q# avec un programme hôte classique externe.</span><span class="sxs-lookup"><span data-stu-id="74e01-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
