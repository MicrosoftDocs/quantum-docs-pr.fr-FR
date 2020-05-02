---
title: Développer avec Q# + C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680162"
---
# <a name="using-q-with-c-and-f"></a>Utilisation de Q # avec\# C et F\#

Q # est conçu pour fonctionner correctement avec les langages .NET tels que C# et F #.
Dans ce guide, nous allons montrer comment utiliser Q # avec un programme hôte écrit dans un langage .NET.

## <a name="prerequisites"></a>Prérequis

- Installez le kit de développement Quantum [pour une utilisation avec des projets en ligne de commande Q #](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Création d’une bibliothèque Q # et d’un hôte .NET

La première étape consiste à créer des projets pour votre bibliothèque Q #, et pour l’hôte .NET qui appellera les opérations et les fonctions définies dans votre bibliothèque Q #.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Créer une nouvelle bibliothèque Q #
  - Accéder au **fichier** -> **nouveau** -> **projet**
  - Tapez « Q # » dans la zone de recherche
  - Sélectionner la **bibliothèque Q #**
  - Sélectionnez **Suivant**.
  - Choisir un nom et un emplacement pour votre bibliothèque
  - Vérifiez que l’option « Placer le projet et la solution dans le même répertoire » n’est pas **cochée** .
  - Sélectionnez **Créer**
- Créer un nouveau programme hôte C# ou F #
  - Accédez à **fichier** → **nouveau** → **projet**
  - Sélectionnez « console App (.NET Core »)» pour C# ou F #
  - Sélectionnez **Suivant**.
  - Sous *solution*, sélectionnez Ajouter à la solution.
  - Choisir un nom pour votre programme hôte
  - Sélectionnez **Créer**

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code ou ligne de commande](#tab/tabid-cmdline)

- Créer une nouvelle bibliothèque Q #

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Créer un projet de console C# ou F #

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Ajoutez votre bibliothèque Q # en tant que référence à partir de votre programme hôte

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Facultatif Créer une solution pour les deux projets

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>Appel de Q # à partir de .NET

Une fois vos projets configurés à l’issue des instructions ci-dessus, vous pouvez appeler Q # à partir de votre application console .NET.
Le compilateur Q # crée des classes .NET pour chaque opération et fonction Q # qui vous permettent d’exécuter vos programmes Quantum sur un simulateur.

Par exemple, l’exemple d' [interopérabilité .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) comprend l’exemple suivant d’une opération Q # :

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Pour appeler cette opération à partir de .NET sur un simulateur Quantum, vous `Run` pouvez utiliser la `RunAlgorithm` méthode de la classe .net générée par le compilateur Q # :

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a>Quelle est l’étape suivante ?

Maintenant que vous avez configuré le kit de développement Quantum pour les deux programmes de ligne de commande Q # et pour l’interopérabilité avec .NET, vous pouvez écrire et exécuter [votre premier programme Quantum](xref:microsoft.quantum.write-program).
