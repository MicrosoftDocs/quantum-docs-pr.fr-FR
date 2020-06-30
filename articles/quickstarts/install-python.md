---
title: Développer en Q# et Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274047"
---
# <a name="develop-with-q-and-python"></a>Développer en Q# et Python

Installez le QDK pour développer des programmes hôtes Python afin d’appeler des opérations Q#.

1. Prérequis

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
  
1. Bien que vous puissiez utiliser Q# avec Python dans n’importe quel IDE, nous vous recommandons vivement d’utiliser l’IDE Visual Studio Code (VS Code) pour vos applications Q# + Python. En utilisant Visual Studio Code et l’extension QDK Visual Studio Code, vous accédez à des fonctionnalités plus riches.

    - Installer [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac)
    - Installez l’[extension QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

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
> * Vous pouvez également utiliser des notebooks Jupyter Python pour écrire le programme Python classique et appeler les opérations Q# à partir des cellules. Le code Python est un programme Python normal.

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
