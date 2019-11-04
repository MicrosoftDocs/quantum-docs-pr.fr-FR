---
title: Installation et validation de la bibliothèque numérique | Microsoft Docs
description: Installation et validation de la bibliothèque de valeurs numériques
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184625"
---
# <a name="numerics-library-installation-and-validation"></a>Installation et validation de la bibliothèque de valeurs numériques

Le kit de développement quantique prend en charge les fonctionnalités numériques via le package NuGet [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .

**> Visual Studio = 2019 :** Si vous utilisez Visual Studio 2019 ou une version ultérieure, vous pouvez ajouter le package de valeurs numériques à l’aide du gestionnaire de package NuGet.
Pour ce faire, sélectionnez « gérer les packages NuGet... ». à partir de l’élément de menu « projet » dans Visual Studio.

Dans l’onglet Parcourir, recherchez le nom du package « Microsoft. Quantum. Numerics ».

> [!NOTE]
> Veillez à cocher « inclure la version préliminaire »

Cela permet de répertorier les packages disponibles au téléchargement.
Le fait de pointer sur « Microsoft. Quantum. Numerics » révèle une flèche pointant vers le bas à droite du numéro de version.
Cliquez sur la flèche pour installer le package numérique.

Pour plus d’informations, consultez le Guide de l' [interface utilisateur du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Vous pouvez également utiliser la console du gestionnaire de package pour ajouter la bibliothèque numérique à votre projet par le biais de l’interface de ligne de commande.

![](~/media/vs2017-nuget-console-menu.png)

À partir de la console du gestionnaire de package, exécutez la commande suivante :

```
Install-Package Microsoft.Quantum.Numerics
```

Pour plus d’informations, consultez le Guide de la [console du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Ligne de commande ou Visual Studio code :** En utilisant la ligne de commande seule ou dans Visual Studio Code, vous pouvez utiliser la commande `dotnet` pour ajouter la référence de package NuGet à votre projet :

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Vérification de votre installation

À l’instar du reste du kit de développement quantique, la bibliothèque de valeurs numériques est fournie avec des exemples qui vous aident à démarrer aussi rapidement que possible.
Pour tester votre installation à l’aide de ces exemples, clonez le [référentiel d’exemples principal](https://github.com/Microsoft/Quantum) , puis exécutez l’un des exemples.

Pour exécuter l’exemple de [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```