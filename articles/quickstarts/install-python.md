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
# <a name="develop-with-q-and-python"></a><span data-ttu-id="523f8-102">Développer en Q# et Python</span><span class="sxs-lookup"><span data-stu-id="523f8-102">Develop with Q# and Python</span></span>

<span data-ttu-id="523f8-103">Installez le QDK pour développer des programmes hôtes Python afin d’appeler des opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="523f8-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="523f8-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="523f8-104">Prerequisites</span></span>

    - <span data-ttu-id="523f8-105">[Python](https://www.python.org/downloads/) 3.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="523f8-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="523f8-106">Le gestionnaire de package Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="523f8-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="523f8-107">Kit SDK .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="523f8-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="523f8-108">Installez le package `qsharp`, un package Python qui assure l’interopérabilité entre Q# et Python.</span><span class="sxs-lookup"><span data-stu-id="523f8-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="523f8-109">Installez IQ#, un noyau utilisé par Jupyter et Python qui offre les fonctionnalités de base nécessaires à la compilation et à l’exécution d’opérations Q#.</span><span class="sxs-lookup"><span data-stu-id="523f8-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="523f8-110">Si vous recevez une erreur durant l’étape `dotnet iqsharp install`, ouvrez une nouvelle fenêtre de terminal et réessayez.</span><span class="sxs-lookup"><span data-stu-id="523f8-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="523f8-111">Si cela ne fonctionne toujours pas, essayez de localiser l’outil `dotnet-iqsharp` installé (sur Windows, `dotnet-iqsharp.exe`) et d’exécuter ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="523f8-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="523f8-112">où `/path/to/dotnet-iqsharp` doit être remplacé par le chemin absolu à l’outil `dotnet-iqsharp` dans votre système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="523f8-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="523f8-113">En général, il se trouve sous `.dotnet/tools` dans le dossier de votre profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="523f8-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="523f8-114">Bien que vous puissiez utiliser Q# avec Python dans n’importe quel IDE, nous vous recommandons vivement d’utiliser l’IDE Visual Studio Code (VS Code) pour vos applications Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="523f8-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="523f8-115">En utilisant Visual Studio Code et l’extension QDK Visual Studio Code, vous accédez à des fonctionnalités plus riches.</span><span class="sxs-lookup"><span data-stu-id="523f8-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="523f8-116">Installer [VS Code](https://code.visualstudio.com/download) (Windows, Linux et Mac)</span><span class="sxs-lookup"><span data-stu-id="523f8-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="523f8-117">Installez l’[extension QDK pour VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="523f8-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="523f8-118">Vérifiez l’installation en créant une application `Hello World`</span><span class="sxs-lookup"><span data-stu-id="523f8-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="523f8-119">Créez une opération Q# minimale en créant un fichier appelé `Operation.qs`et en y ajoutant le code suivant :</span><span class="sxs-lookup"><span data-stu-id="523f8-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="523f8-120">Créez un programme Python appelé `hello_world.py` pour appeler l’opération `SayHello()` en Q#  :</span><span class="sxs-lookup"><span data-stu-id="523f8-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="523f8-121">Exécutez le programme :</span><span class="sxs-lookup"><span data-stu-id="523f8-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="523f8-122">Vérifiez la sortie.</span><span class="sxs-lookup"><span data-stu-id="523f8-122">Verify the output.</span></span> <span data-ttu-id="523f8-123">Votre programme doit générer les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="523f8-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="523f8-124">Vous pouvez également utiliser des notebooks Jupyter Python pour écrire le programme Python classique et appeler les opérations Q# à partir des cellules.</span><span class="sxs-lookup"><span data-stu-id="523f8-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="523f8-125">Le code Python est un programme Python normal.</span><span class="sxs-lookup"><span data-stu-id="523f8-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="523f8-126">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="523f8-126">Next steps</span></span>

<span data-ttu-id="523f8-127">Maintenant que vous avez installé le Quantum Development Kit dans votre environnement préféré, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="523f8-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
