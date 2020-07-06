---
title: Développer avec Q# et .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 714c15d9589095f0fe395fcd6941672167879dca
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885507"
---
# <a name="develop-with-q-and-net"></a>Développer avec Q# et .NET

Q# est conçu pour fonctionner avec les langages .NET tels que C# et F#.
Dans ce guide, nous allons vous montrer comment utiliser Q# avec un programme hôte écrit dans un langage .NET.

Tout d’abord, nous allons créer l’application Q# et l’hôte .NET, puis nous allons expliquer comment appeler le code Q# à partir de l’hôte.

## <a name="prerequisites"></a>Prérequis

- Installez le kit de développement Quantum [pour une utilisation avec les projets en ligne de commande Q#](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Création d’une bibliothèque Q# et d’un hôte .NET

La première étape consiste à créer des projets pour votre bibliothèque Q# et pour l’hôte .NET qui appellera les opérations et les fonctions définies dans votre bibliothèque Q#.

Suivez les instructions situées sous l’onglet correspondant à votre environnement de développement.
Si vous utilisez un éditeur autre que Visual Studio ou VS Code, suivez les étapes pour la ligne de commande.

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code ou ligne de commande](#tab/tabid-cmdline)

- Créer une bibliothèque Q#

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Créer un projet console C# ou F#

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Ajouter votre bibliothèque Q# comme référence à partir de votre programme hôte

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [Facultatif] Créer une solution pour les deux projets

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Créer une bibliothèque Q#
  - Accédez à **Fichier** -> **Nouveau** -> **Projet**
  - Tapez « Q# » dans la zone de recherche.
  - Sélectionnez **Bibliothèque Q#** .
  - Sélectionnez **Suivant**.
  - Choisissez un nom et un emplacement pour votre bibliothèque.
  - Vérifiez que l’option « Placer la solution et le projet dans le même répertoire » est **décochée**.
  - Sélectionnez **Créer**
- Créer un programme hôte C# ou F#
  - Accédez à **Fichier** → **Nouveau** → **Projet**.
  - Sélectionnez Application console (.NET Core) pour C# ou F#.
  - Sélectionnez **Suivant**.
  - Sous *Solution*, sélectionnez Ajouter à la solution.
  - Choisissez un nom pour votre programme hôte.
  - Sélectionnez **Créer**

***

## <a name="calling-into-q-from-net"></a>Appel de Q# à partir de .NET

Une fois vos projets configurés à l’aide des instructions ci-dessus, vous pouvez appeler Q# à partir de votre application console .NET.
Le compilateur Q# crée des classes .NET pour chaque opération et fonction Q# qui vous permettent d’exécuter vos programmes quantiques sur un simulateur.

Par exemple, l’[exemple d’interopérabilité .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) comprend l’exemple suivant d’une opération Q# :

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Pour appeler cette opération à partir de .NET sur un simulateur quantique, vous pouvez utiliser la méthode `Run` de la classe .NET `RunAlgorithm` générée par le compilateur Q# :

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez configuré le kit de développement Quantum pour les deux programmes en ligne de commande Q# et pour l’interopérabilité avec .NET, vous pouvez écrire et exécuter [votre premier programme quantique](xref:microsoft.quantum.quickstarts.qrng).
