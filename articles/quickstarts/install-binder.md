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
# <a name="develop-with-no-locq-and-binder"></a>Développer en Q# et Binder

Vous pouvez utiliser Binder pour exécuter et partager vos blocs-notes Jupyter en ligne.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Utiliser Binder avec les exemples Microsoft QDK

Pour configurer automatiquement Binder afin d’utiliser les exemples Microsoft QDK :

1. Ouvrez un navigateur, puis exécutez https://aka.ms/try-qsharp.
1. Sur la page d’accueil **Exemples du Quantum Development Kit**, cliquez sur **Q# bloc-notes** pour apprendre à utiliser IQ# pour écrire vos propres blocs-notes d’applications quantiques.

![Page d’accueil QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>Utiliser Binder avec vos propres blocs-notes et référentiel

Si vous avez déjà des blocs-notes dans un référentiel GitHub, vous pouvez configurer Binder pour qu’il fonctionne avec votre référentiel :

1. Assurez-vous qu’il existe un fichier nommé *Dockerfile* à la racine de votre référentiel. Le fichier doit contenir au moins les lignes suivantes :

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > Vous pouvez vérifier la version la plus récente de IQ# dans les [notes de publication](xref:microsoft.quantum.relnotes).

    Pour plus d’informations sur la création d’un Dockerfile, consultez la [référence Dockerfile](https://docs.docker.com/engine/reference/builder/).

2. Ouvrez un navigateur pour accéder à [mybinder.org](https://mybinder.org).
3. Entrez le nom de votre référentiel comme **URL GitHub** (par exemple, *MonNom/MonRéférentiel*), puis cliquez sur **lancer**.

![Formulaire MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez configuré votre environnement Binder, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
