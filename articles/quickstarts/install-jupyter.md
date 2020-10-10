---
title: Développer avec des notebooks Jupyter Q#
description: Découvrez comment créer une application Q# à l’aide de Jupyter Notebook.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: b34d89ab33a4644c1dd4342949685f9bf84babd8
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771402"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a>Développer avec des notebooks Jupyter Q#

Installez le QDK pour le développement d’opérations Q# sur des notebooks Jupyter Q#.

Les notebooks Jupyter permettent l’exécution de code sur place avec les instructions, les notes et autre contenu. Cet environnement est idéal pour écrire du code Q# avec des explications incorporées ou des tutoriels interactifs sur l’informatique quantique. Voici ce que vous devez faire pour commencer à créer vos propres notebooks Q#.

## <a name="install-the-ino-locq-jupyter-kernel"></a>Installer le noyau Jupyter IQ#

IQ# (prononcé aïe-quiou-sharp) est une extension principalement utilisée par Jupyter et Python avec le SDK .NET Core qui offre les fonctionnalités de base nécessaires à la compilation et à la simulation des opérations Q#.

### <a name="install-using-conda-recommended"></a>[Installation à l’aide de conda (recommandé)](#tab/tabid-conda)

1. Installez [Miniconda](https://docs.conda.io/en/latest/miniconda.html) ou [Anaconda](https://www.anaconda.com/products/individual#Downloads). **Remarque :** Installation 64 bits requise.

1. Ouvrez une invite Anaconda.

   - Si vous préférez utiliser PowerShell ou pwsh : ouvrez un interpréteur de commandes, exécutez `conda init powershell`, puis fermez et rouvrez l’interpréteur

1. Créez puis activez un nouvel environnement conda nommé `qsharp-env` avec les packages nécessaires (y compris Jupyter Notebook et IQ#) en exécutant les commandes suivantes :

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Exécutez `python -c "import qsharp"` à partir du même terminal pour vérifier votre installation et ajouter à votre cache de package local tous les composants QDK nécessaires.

### <a name="install-using-net-cli-advanced"></a>[Installation à l’aide de l’interface CLI .NET (avancé)](#tab/tabid-dotnetcli)

1. Configuration requise :

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [Kit SDK .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installez le package `Microsoft.Quantum.IQSharp`.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> Si vous recevez une erreur durant l’étape `dotnet iqsharp install`, ouvrez une nouvelle fenêtre de terminal et réessayez.
> Si cela ne fonctionne toujours pas, essayez de localiser l’outil `dotnet-iqsharp` installé (sur Windows, `dotnet-iqsharp.exe`) et d’exécuter ce qui suit :
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> où `/path/to/dotnet-iqsharp` doit être remplacé par le chemin absolu à l’outil `dotnet-iqsharp` dans votre système de fichiers.
> En général, il se trouve sous `.dotnet/tools` dans le dossier de votre profil utilisateur.
    
***

Et voilà ! Vous disposez maintenant du noyau IQ# pour Jupyter, qui fournit les fonctionnalités de base pour la compilation et l’exécution des opérations Q# à partir des notebooks Jupyter Q#.

## <a name="create-your-first-no-locq-notebook"></a>Créer votre premier notebook Q#

Vous êtes maintenant prêt à vérifier l’installation de Jupyter Notebook Q# en écrivant et en exécutant une simple opération Q#.

1. À partir de l’environnement que vous avez créé lors de l’installation (c’est-à-dire, soit l’environnement conda que vous avez créé, soit l’environnement Python dans lequel vous avez installé Jupyter), exécutez la commande suivante pour démarrer le serveur Jupyter Notebook :

    ```
    jupyter notebook
    ```

    - Si le notebook Jupyter ne s’ouvre pas automatiquement dans votre navigateur, copiez et collez l’URL fournie par la ligne de commande dans votre navigateur.

1. Choisissez **Nouveau → Q#** pour créer un Jupyter Notebook avec un noyau Q#, puis ajoutez le code suivant à la première cellule du notebook :

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Exécutez cette cellule du notebook :

    ![Cellule de Jupyter Notebook avec code Q#](~/media/install-guide-jupyter.png)

    Vous devriez voir `SampleQuantumRandomNumberGenerator` dans la sortie de la cellule. Lorsqu’il est exécuté dans Jupyter Notebook, le code Q# est compilé et la cellule affiche le nom des opérations qu’il trouve.

1. Dans une nouvelle cellule, exécutez l’opération que vous venez de créer (dans un simulateur) à l’aide de la commande `%simulate` :

    ![Cellule de notebook Jupyter avec commande magic %simulate](~/media/install-guide-jupyter-simulate.png)

    Vous devez voir le résultat de l’opération que vous avez appelée. Dans ce cas, étant donné que votre opération génère un résultat aléatoire, vous verrez soit `Zero`, soit `One` à l’écran. Si vous exécutez la cellule à plusieurs reprises, vous devriez voir chaque résultat environ une fois sur deux.

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le QDK pour les notebooks Jupyter Q#, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng) en écrivant du code Q# directement dans l’environnement Jupyter Notebook.

Pour obtenir plus d’exemples de ce que vous pouvez faire avec des notebooks Jupyter Q#, consultez les rubriques suivantes :

- [Présentation de Q# et de Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/) Vous y trouverez un notebook Jupyter Q# qui montre en détail comment utiliser du code Q# dans l’environnement Jupyter.
- [Katas Quantum](xref:microsoft.quantum.overview.katas), une collection open source de tutoriels auto-rythmés et d’exercices de programmation sous la forme de notebooks Jupyter Q#. Les [notebooks des katas Quantum](https://github.com/microsoft/QuantumKatas#tutorial-topics) sont un bon point de départ. Les katas Quantum sont conçus pour vous inculquer des notions de l’informatique quantique et de la programmation en Q#. Ils constituent un excellent exemple du type de contenu que vous pouvez créer avec des notebooks Jupyter Q#.
