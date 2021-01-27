---
title: Installation du kit de développement Microsoft Quantum (QDK)
description: Découvrez comment installer le kit de développement Microsoft Quantum pour différents environnements.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859024"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="fa36a-103">Installation du kit de développement Microsoft Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="fa36a-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="fa36a-104">Découvrez comment installer le kit de développement Microsoft Quantum (QDK) dans votre environnement afin de pouvoir vous lancer dans la programmation quantique.</span><span class="sxs-lookup"><span data-stu-id="fa36a-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="fa36a-105">Le QDK se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="fa36a-105">The QDK consists of:</span></span>

- <span data-ttu-id="fa36a-106">Langage de programmation Q#</span><span class="sxs-lookup"><span data-stu-id="fa36a-106">The Q# programming language</span></span>
- <span data-ttu-id="fa36a-107">Ensemble de bibliothèques qui résument des fonctionnalités complexes en Q#</span><span class="sxs-lookup"><span data-stu-id="fa36a-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="fa36a-108">API pour Python et les langages .NET (C#, F# et VB.NET) pour exécuter des programmes quantiques écrits en Q#</span><span class="sxs-lookup"><span data-stu-id="fa36a-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="fa36a-109">Outils pour faciliter votre développement</span><span class="sxs-lookup"><span data-stu-id="fa36a-109">Tools to facilitate your development</span></span>

<span data-ttu-id="fa36a-110">Les programmes Q# peuvent être exécutés en tant qu’applications autonomes avec Visual Studio Code ou Visual Studio, via des notebooks Jupyter avec le noyau Jupyter IQ# ou couplés avec un programme hôte écrit en Python ou en langage .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="fa36a-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="fa36a-111">Vous pouvez aussi exécuter les programmes Q# en ligne avec [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) ou [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="fa36a-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="fa36a-112">Options pour installer le QDK</span><span class="sxs-lookup"><span data-stu-id="fa36a-112">Options for setting up the QDK</span></span>

<span data-ttu-id="fa36a-113">Vous pouvez utiliser le QDK de trois manières :</span><span class="sxs-lookup"><span data-stu-id="fa36a-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="fa36a-114">Installer le QDK localement</span><span class="sxs-lookup"><span data-stu-id="fa36a-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="fa36a-115">Utiliser le QDK en ligne</span><span class="sxs-lookup"><span data-stu-id="fa36a-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="fa36a-116">Utiliser une image Docker du QDK</span><span class="sxs-lookup"><span data-stu-id="fa36a-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="fa36a-117">Installer le QDK localement</span><span class="sxs-lookup"><span data-stu-id="fa36a-117">Install the QDK locally</span></span>

<span data-ttu-id="fa36a-118">Vous pouvez développer le code Q# dans la plupart de vos IDE préférés et intégrer Q# dans d’autres langages comme Python et .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="fa36a-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="fa36a-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="fa36a-119"><b>VS Code</span></span><br><span data-ttu-id="fa36a-120">(2019 ou ultérieur)</b></span><span class="sxs-lookup"><span data-stu-id="fa36a-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="fa36a-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa36a-121"><b>Visual Studio</span></span><br><span data-ttu-id="fa36a-122">(2019 ou ultérieur)</b></span><span class="sxs-lookup"><span data-stu-id="fa36a-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="fa36a-123"><b>Blocs-notes Jupyter</b></span><span class="sxs-lookup"><span data-stu-id="fa36a-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="fa36a-124"><b>Ligne de commande</b></span><span class="sxs-lookup"><span data-stu-id="fa36a-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="fa36a-125"><b>Prise en charge du système d’exploitation :</b></span><span class="sxs-lookup"><span data-stu-id="fa36a-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="fa36a-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="fa36a-127">Windows uniquement</span><span class="sxs-lookup"><span data-stu-id="fa36a-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="fa36a-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="fa36a-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="fa36a-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="fa36a-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="fa36a-130"><b>Q# autonome</b></span><span class="sxs-lookup"><span data-stu-id="fa36a-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-131"><a href="xref:microsoft.quantum.install.standalone">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-132"><a href="xref:microsoft.quantum.install.standalone">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-133"><a href="xref:microsoft.quantum.install.jupyter">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-134"><a href="xref:microsoft.quantum.install.standalone">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="fa36a-135"><b>Q# et Python</b></span><span class="sxs-lookup"><span data-stu-id="fa36a-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-136"><a href="xref:microsoft.quantum.install.python">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-137"><a href="xref:microsoft.quantum.install.python">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-138"><a href="xref:microsoft.quantum.install.python">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-139"><a href="xref:microsoft.quantum.install.python">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="fa36a-140"><b>Q# et .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="fa36a-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="fa36a-141"><a href="xref:microsoft.quantum.install.cs">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-142"><a href="xref:microsoft.quantum.install.cs">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="fa36a-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="fa36a-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="fa36a-144"><a href="xref:microsoft.quantum.install.cs">Installer</a></span><span class="sxs-lookup"><span data-stu-id="fa36a-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="fa36a-145">Utiliser le QDK en ligne</span><span class="sxs-lookup"><span data-stu-id="fa36a-145">Use the QDK Online</span></span>

<span data-ttu-id="fa36a-146">Vous pouvez également développer le code Q# sans rien installer localement avec les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="fa36a-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="fa36a-147">Ressource</span><span class="sxs-lookup"><span data-stu-id="fa36a-147">Resource</span></span>|<span data-ttu-id="fa36a-148">Avantages</span><span class="sxs-lookup"><span data-stu-id="fa36a-148">Advantages</span></span>|<span data-ttu-id="fa36a-149">Limites</span><span class="sxs-lookup"><span data-stu-id="fa36a-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="fa36a-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="fa36a-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="fa36a-151">Environnement de développement en ligne complet</span><span class="sxs-lookup"><span data-stu-id="fa36a-151">A rich online development environment</span></span>  |<span data-ttu-id="fa36a-152">Nécessite un plan et un abonnement Azure</span><span class="sxs-lookup"><span data-stu-id="fa36a-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="fa36a-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="fa36a-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="fa36a-154">Expérience de notebook en ligne gratuite</span><span class="sxs-lookup"><span data-stu-id="fa36a-154">Free online notebook experience</span></span> |<span data-ttu-id="fa36a-155">Aucune persistance</span><span class="sxs-lookup"><span data-stu-id="fa36a-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="fa36a-156">Utiliser le QDK avec Docker</span><span class="sxs-lookup"><span data-stu-id="fa36a-156">Use the QDK with Docker</span></span>

<span data-ttu-id="fa36a-157">Vous pouvez utiliser notre image Docker du QDK dans votre installation Docker locale ou dans le cloud via un service prenant en charge les images Docker, par exemple ACI.</span><span class="sxs-lookup"><span data-stu-id="fa36a-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="fa36a-158">Vous pouvez télécharger l’image Docker IQ# depuis https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="fa36a-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="fa36a-159">Vous pouvez aussi utiliser Docker avec un conteneur de développement distant Visual Studio Code pour définir rapidement des environnements de développement.</span><span class="sxs-lookup"><span data-stu-id="fa36a-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="fa36a-160">Pour plus d’informations sur les conteneurs de développement VS Code, consultez https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="fa36a-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fa36a-161">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="fa36a-161">Next steps</span></span>

<span data-ttu-id="fa36a-162">Le workflow de chacune de ces configurations est décrit et comparé aux autres dans [Méthodes d’exécution d’un programme Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="fa36a-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
