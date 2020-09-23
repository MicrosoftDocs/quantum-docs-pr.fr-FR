---
title: Installation du kit de développement Microsoft Quantum (QDK)
description: Découvrez comment installer le kit de développement Microsoft Quantum pour différents environnements.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834480"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="f8ff7-103">Installation du kit de développement Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="f8ff7-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="f8ff7-104">Découvrez comment installer le kit de développement Microsoft Quantum (QDK) dans votre environnement afin de pouvoir vous lancer dans la programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="f8ff7-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="f8ff7-105">Le QDK se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f8ff7-105">The QDK consists of:</span></span>

- <span data-ttu-id="f8ff7-106">Langage de programmation Q#</span><span class="sxs-lookup"><span data-stu-id="f8ff7-106">The Q# programming language</span></span>
- <span data-ttu-id="f8ff7-107">Ensemble de bibliothèques qui résument des fonctionnalités complexes en Q#</span><span class="sxs-lookup"><span data-stu-id="f8ff7-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="f8ff7-108">API pour Python et les langages .NET (C#, F# et VB.NET) pour exécuter des programmes quantiques écrits en Q#</span><span class="sxs-lookup"><span data-stu-id="f8ff7-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="f8ff7-109">Outils pour faciliter votre développement</span><span class="sxs-lookup"><span data-stu-id="f8ff7-109">Tools to facilitate your development</span></span>

<span data-ttu-id="f8ff7-110">Les programmes Q# peuvent être exécutés en tant qu’applications autonomes avec Visual Studio Code ou Visual Studio, via des notebooks Jupyter avec le noyau Jupyter IQ# ou couplés avec un programme hôte écrit en Python ou en langage .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="f8ff7-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="f8ff7-111">Vous pouvez aussi exécuter les programmes Q# en ligne avec [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) ou [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="f8ff7-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="f8ff7-112">Options pour installer le QDK</span><span class="sxs-lookup"><span data-stu-id="f8ff7-112">Options for setting up the QDK</span></span>

<span data-ttu-id="f8ff7-113">Vous pouvez utiliser le QDK de trois manières :</span><span class="sxs-lookup"><span data-stu-id="f8ff7-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="f8ff7-114">Installer le QDK localement</span><span class="sxs-lookup"><span data-stu-id="f8ff7-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="f8ff7-115">Utiliser le QDK en ligne</span><span class="sxs-lookup"><span data-stu-id="f8ff7-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="f8ff7-116">Utiliser une image Docker du QDK</span><span class="sxs-lookup"><span data-stu-id="f8ff7-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="f8ff7-117">Installer le QDK localement</span><span class="sxs-lookup"><span data-stu-id="f8ff7-117">Install the QDK locally</span></span>

<span data-ttu-id="f8ff7-118">Vous pouvez développer le code Q# dans la plupart de vos IDE préférés et intégrer Q# dans d’autres langages comme Python et .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="f8ff7-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="f8ff7-119">**VS Code<br>(2019 ou ultérieur)**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="f8ff7-120">**Visual Studio<br>(2019 ou ultérieur)**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="f8ff7-121">**Blocs-notes Jupyter**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="f8ff7-122">**Ligne de commande**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="f8ff7-123">**SE**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-123">**OS**</span></span> |<span data-ttu-id="f8ff7-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="f8ff7-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="f8ff7-125">Windows uniquement</span><span class="sxs-lookup"><span data-stu-id="f8ff7-125">Windows only</span></span> |<span data-ttu-id="f8ff7-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="f8ff7-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="f8ff7-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="f8ff7-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="f8ff7-128">**Q# autonome**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="f8ff7-129">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="f8ff7-130">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="f8ff7-131">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="f8ff7-132">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="f8ff7-133">**Q# et Python**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-133">**Q#  and Python**</span></span> |[<span data-ttu-id="f8ff7-134">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="f8ff7-135">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="f8ff7-136">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="f8ff7-137">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="f8ff7-138">**Q# et .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="f8ff7-139">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="f8ff7-140">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="f8ff7-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="f8ff7-141">&#10006;</span></span> |[<span data-ttu-id="f8ff7-142">Installer</span><span class="sxs-lookup"><span data-stu-id="f8ff7-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="f8ff7-143">Utiliser le QDK en ligne</span><span class="sxs-lookup"><span data-stu-id="f8ff7-143">Use the QDK Online</span></span>

<span data-ttu-id="f8ff7-144">Vous pouvez également développer le code Q# sans rien installer localement avec les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8ff7-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="f8ff7-145">Ressource</span><span class="sxs-lookup"><span data-stu-id="f8ff7-145">Resource</span></span>|<span data-ttu-id="f8ff7-146">Avantages</span><span class="sxs-lookup"><span data-stu-id="f8ff7-146">Advantages</span></span>|<span data-ttu-id="f8ff7-147">Limites</span><span class="sxs-lookup"><span data-stu-id="f8ff7-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="f8ff7-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="f8ff7-149">Environnement de développement en ligne complet</span><span class="sxs-lookup"><span data-stu-id="f8ff7-149">A rich online development environment</span></span>  |<span data-ttu-id="f8ff7-150">Nécessite un plan et un abonnement Azure</span><span class="sxs-lookup"><span data-stu-id="f8ff7-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="f8ff7-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="f8ff7-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="f8ff7-152">Expérience de notebook en ligne gratuite</span><span class="sxs-lookup"><span data-stu-id="f8ff7-152">Free online notebook experience</span></span> |<span data-ttu-id="f8ff7-153">Aucune persistance</span><span class="sxs-lookup"><span data-stu-id="f8ff7-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="f8ff7-154">Utiliser le QDK avec Docker</span><span class="sxs-lookup"><span data-stu-id="f8ff7-154">Use the QDK with Docker</span></span>

<span data-ttu-id="f8ff7-155">Vous pouvez utiliser notre image Docker du QDK dans votre installation Docker locale ou dans le cloud via un service prenant en charge les images Docker, par exemple ACI.</span><span class="sxs-lookup"><span data-stu-id="f8ff7-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="f8ff7-156">Vous pouvez télécharger l’image Docker IQ# depuis https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="f8ff7-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="f8ff7-157">Vous pouvez aussi utiliser Docker avec un conteneur de développement distant Visual Studio Code pour définir rapidement des environnements de développement.</span><span class="sxs-lookup"><span data-stu-id="f8ff7-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="f8ff7-158">Pour plus d’informations sur les conteneurs de développement VS Code, consultez https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="f8ff7-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8ff7-159">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="f8ff7-159">Next steps</span></span>

<span data-ttu-id="f8ff7-160">Le workflow de chacune de ces configurations est décrit et comparé aux autres dans [Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="f8ff7-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
