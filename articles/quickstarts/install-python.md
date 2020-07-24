---
title: Développer en Q# et Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: ec5e66e0c85d89888a8ff1e7d6bf18bf89ff44ac
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871584"
---
# <a name="develop-with-q-and-python"></a>Développer en Q# et Python

Installez le QDK pour développer des programmes hôtes Python afin d’appeler des opérations Q#.

## <a name="install-the-qsharp-python-package"></a>Installer le package Python `qsharp`

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

### <a name="install-using-net-cli-and-pip-advanced"></a>[Installation à l’aide de l’interface CLI .NET et de pip (avancé)](#tab/tabid-dotnetcli)

1. Configuration requise :

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [Kit SDK .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Installez le package `qsharp`, un package Python qui assure l’interopérabilité entre Q# et Python.

    ```
    pip install qsharp
    ```

1. Installez IQ#, un noyau utilisé par Jupyter et Python qui offre les fonctionnalités de base nécessaires à la compilation et à l’exécution d’opérations Q#.

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

Et voilà ! Vous disposez maintenant du package Python `qsharp` et du noyau IQ# pour Jupyter, qui fournit les fonctionnalités de base pour la compilation et l’exécution des opérations Q# à partir de Python et vous permet d’utiliser les notebooks Jupyter Q#.

## <a name="choose-your-ide"></a>Choisir votre IDE

Bien que vous puissiez utiliser Q# avec Python dans n’importe quel IDE, nous vous recommandons vivement d’utiliser l’IDE Visual Studio Code (VS Code) pour vos applications Q# + Python. L’extension Visual Studio Code QDK vous permet de tirer parti de fonctionnalités plus riches, telles que les avertissements, la coloration syntaxique, les modèles de projets, etc.

Si vous souhaitez utiliser VS Code :

- Installez [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac).
- Installez l’[extension QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Si vous souhaitez utiliser un autre éditeur, les instructions ci-dessus vous indiqueront tout ce que vous avez besoin de savoir.

## <a name="write-your-first-q-program"></a>Écrire votre premier programme Q#

Vous êtes maintenant prêt à vérifier l’installation de votre package Python `qsharp` en écrivant et en exécutant un programme Q# simple.

1. Créez une opération Q# minimale en créant un fichier appelé `Operation.qs` et en y ajoutant le code suivant :

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. Dans le même dossier que `Operation.qs`, créez un programme Python appelé `host.py` pour simuler l’opération Q# `SampleQuantumRandomNumberGenerator()` :

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. À partir de l’environnement que vous avez créé lors de l’installation (c’est-à-dire, l’environnement conda ou l’environnement Python dans lequel vous avez installé `qsharp`), exécutez le programme :

    ```
    python host.py
    ```

1. Vous devez voir le résultat de l’opération que vous avez appelée. Dans ce cas, étant donné que votre opération génère un résultat aléatoire, vous verrez soit `Zero`, soit `One` à l’écran. Si vous exécutez le programme à plusieurs reprises, vous devriez voir chaque résultat environ une fois sur deux.

> [!NOTE]
> * Le code Python est un programme Python normal. Pour écrire le programme Python et appeler les opérations Q#, vous pouvez utiliser n’importe quel environnement Python, y compris les notebooks Jupyter basés sur Python. Le programme Python peut importer des opérations Q# à partir de n’importe quel fichier .qs situé dans le même dossier que le code Python.

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez suivre ce tutoriel en vue d’écrire et d’exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
