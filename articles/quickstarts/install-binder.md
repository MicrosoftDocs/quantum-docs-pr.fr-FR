---
title: Développer en Q# et Binder
description: Découvrez comment créer une application Q# à l’aide de Binder.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836535"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="c8fff-103">Développer en Q# et Binder</span><span class="sxs-lookup"><span data-stu-id="c8fff-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="c8fff-104">Vous pouvez utiliser Binder pour exécuter et partager vos blocs-notes Jupyter en ligne.</span><span class="sxs-lookup"><span data-stu-id="c8fff-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="c8fff-105">Utiliser Binder avec les exemples Microsoft QDK</span><span class="sxs-lookup"><span data-stu-id="c8fff-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="c8fff-106">Pour configurer automatiquement Binder afin d’utiliser les exemples Microsoft QDK :</span><span class="sxs-lookup"><span data-stu-id="c8fff-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="c8fff-107">Ouvrez un navigateur, puis exécutez https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="c8fff-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="c8fff-108">Sur la page d’accueil **Exemples du Quantum Development Kit**, cliquez sur **Q# bloc-notes** pour apprendre à utiliser IQ# pour écrire vos propres blocs-notes d’applications quantiques.</span><span class="sxs-lookup"><span data-stu-id="c8fff-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![Page d’accueil QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="c8fff-110">Utiliser Binder avec vos propres blocs-notes et référentiel</span><span class="sxs-lookup"><span data-stu-id="c8fff-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="c8fff-111">Si vous avez déjà des blocs-notes dans un référentiel GitHub, vous pouvez configurer Binder pour qu’il fonctionne avec votre référentiel :</span><span class="sxs-lookup"><span data-stu-id="c8fff-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="c8fff-112">Assurez-vous qu’il existe un fichier nommé *Dockerfile* à la racine de votre référentiel.</span><span class="sxs-lookup"><span data-stu-id="c8fff-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="c8fff-113">Le fichier doit contenir au moins les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8fff-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="c8fff-114">Vous pouvez vérifier la version la plus récente de IQ# dans les [notes de publication](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="c8fff-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="c8fff-115">Pour plus d’informations sur la création d’un Dockerfile, consultez la [référence Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="c8fff-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="c8fff-116">Ouvrez un navigateur pour accéder à [mybinder.org](https://mybinder.org).</span><span class="sxs-lookup"><span data-stu-id="c8fff-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="c8fff-117">Entrez le nom de votre référentiel comme **URL GitHub** (par exemple, *MonNom/MonRéférentiel*), puis cliquez sur **lancer**.</span><span class="sxs-lookup"><span data-stu-id="c8fff-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![Formulaire MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="c8fff-119">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="c8fff-119">Next steps</span></span>

<span data-ttu-id="c8fff-120">Maintenant que vous avez configuré votre environnement Binder, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="c8fff-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
