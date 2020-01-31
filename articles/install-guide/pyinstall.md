---
title: 'Développer avec Q # + python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76830999"
---
# <a name="develop-with-q--python"></a>Développer avec Q # + python

Installez le QDK pour développer des programmes hôtes Python afin d’appeler les opérations Q #.

1. Prérequis

    - [Python](https://www.python.org/downloads/) 3.6 ou version ultérieure
    - Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [Kit SDK .NET Core 3,1 ou version ultérieure](https://www.microsoft.com/net/download)


1. Installez le package `qsharp`, un package Python qui permet l’interopérabilité entre Q # et Python.

    ```bash
    pip install qsharp
    ```

1. Installez `iqsharp`, un noyau utilisé par Jupyter et Python qui fournit les fonctionnalités de base pour la compilation et l’exécution des opérations Q #.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
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

        ```bash
        python hello_world.py
        ```

    - Vérifiez la sortie. Votre programme doit générer les lignes suivantes :

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * Vous pouvez également utiliser des blocs-notes python Jupyter pour écrire le programme python classique et appeler des opérations Q # à partir des cellules. Le code python n’est qu’un programme python normal.

## <a name="whats-next"></a>Et ensuite ?

Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).
