---
title: 'Développer avec Q # et Python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630285"
---
# <a name="develop-with-q-and-python"></a>Développer avec Q # et Python

Installez le QDK pour développer des programmes hôtes Python afin d’appeler les opérations Q #.

1. Prérequis

    - [Python](https://www.python.org/downloads/) 3,6 ou version ultérieure
    - Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [Kit SDK .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Installez le `qsharp` package, un package Python qui permet l’interopérabilité entre Q # et Python.

    ```
    pip install qsharp
    ```

1. Installez IQ #, un noyau utilisé par Jupyter et Python qui fournit les fonctionnalités de base pour la compilation et l’exécution des opérations Q #.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Si vous recevez une erreur lors de l' `dotnet iqsharp install` étape, ouvrez une nouvelle fenêtre de terminal, puis réessayez.
    > Si cela ne fonctionne toujours pas, essayez de localiser l' `dotnet-iqsharp` outil installé (sur Windows `dotnet-iqsharp.exe` ) et d’exécuter :
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > où `/path/to/dotnet-iqsharp` doit être remplacé par le chemin d’accès absolu à l' `dotnet-iqsharp` outil dans votre système de fichiers.
    > En général, il se trouve sous `.dotnet/tools` dans votre dossier de profil utilisateur.
  
1. Bien que vous puissiez utiliser Q # avec Python dans n’importe quel IDE, nous vous recommandons vivement d’utiliser l’IDE Visual Studio Code (VS Code) pour vos applications r # + Python. En utilisant Visual Studio Code et l’extension QDK Visual Studio Code vous accédez à des fonctionnalités plus riches.

    - Installer [vs code](https://code.visualstudio.com/download) (Windows, Linux et Mac)
    - Installez l' [extension QDK pour vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Vérifiez l’installation en créant une application `Hello World`

    - Créez une opération Q# minimale en créant un fichier appelé `Operation.qs`et en y ajoutant le code suivant :

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - Créez un programme Python appelé `hello_world.py` pour appeler l’opération `SayHello()` en Q#  :

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Exécutez le programme :

        ```
        python hello_world.py
        ```

    - Vérifiez la sortie. Votre programme doit générer les lignes suivantes :

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Vous pouvez également utiliser des blocs-notes python Jupyter pour écrire le programme python classique et appeler des opérations Q # à partir des cellules. Le code python n’est qu’un programme python normal.

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
