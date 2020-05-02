---
title: Développer avec Q# + Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: e1b8a0c68b3ac0c059c6de6e478593321764ff88
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680143"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="0c712-102">Développer avec Q# + Python</span><span class="sxs-lookup"><span data-stu-id="0c712-102">Develop with Q# + Python</span></span>

<span data-ttu-id="0c712-103">Installez le QDK pour développer des programmes hôtes Python afin d’appeler les opérations Q #.</span><span class="sxs-lookup"><span data-stu-id="0c712-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="0c712-104">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="0c712-104">Pre-requisites</span></span>

    - <span data-ttu-id="0c712-105">[Python](https://www.python.org/downloads/) 3,6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="0c712-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="0c712-106">Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="0c712-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="0c712-107">Kit SDK .NET Core 3,1 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="0c712-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="0c712-108">Installez le `qsharp` package, un package Python qui permet l’interopérabilité entre Q # et Python.</span><span class="sxs-lookup"><span data-stu-id="0c712-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="0c712-109">Installez IQ #, un noyau utilisé par Jupyter et Python qui fournit les fonctionnalités de base pour la compilation et l’exécution des opérations Q #.</span><span class="sxs-lookup"><span data-stu-id="0c712-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="0c712-110">Bien que vous puissiez utiliser Q # avec Python dans n’importe quel IDE, nous vous recommandons vivement d’utiliser l’IDE Visual Studio Code (VS Code) pour vos applications r # + Python.</span><span class="sxs-lookup"><span data-stu-id="0c712-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="0c712-111">En utilisant Visual Studio Code et l’extension QDK Visual Studio Code vous accédez à des fonctionnalités plus riches.</span><span class="sxs-lookup"><span data-stu-id="0c712-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="0c712-112">Installer [vs code](https://code.visualstudio.com/download) (Windows, Linux et Mac)</span><span class="sxs-lookup"><span data-stu-id="0c712-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="0c712-113">Installez l' [extension QDK pour vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="0c712-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="0c712-114">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="0c712-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="0c712-115">Créez une opération Q# minimale en créant un fichier appelé `Operation.qs`et en y ajoutant le code suivant :</span><span class="sxs-lookup"><span data-stu-id="0c712-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="0c712-116">Créez un programme Python appelé `hello_world.py` pour appeler l’opération `SayHello()` en Q#  :</span><span class="sxs-lookup"><span data-stu-id="0c712-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="0c712-117">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="0c712-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="0c712-118">Vérifiez la sortie.</span><span class="sxs-lookup"><span data-stu-id="0c712-118">Verify the output.</span></span> <span data-ttu-id="0c712-119">Votre programme doit générer les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c712-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="0c712-120">Vous pouvez également utiliser des blocs-notes python Jupyter pour écrire le programme python classique et appeler des opérations Q # à partir des cellules.</span><span class="sxs-lookup"><span data-stu-id="0c712-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="0c712-121">Le code python n’est qu’un programme python normal.</span><span class="sxs-lookup"><span data-stu-id="0c712-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="0c712-122">Quelle est l’étape suivante ?</span><span class="sxs-lookup"><span data-stu-id="0c712-122">What's next?</span></span>

<span data-ttu-id="0c712-123">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="0c712-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
