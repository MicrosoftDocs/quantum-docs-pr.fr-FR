---
title: 'Utilisation de bibliothèques Q # supplémentaires'
description: 'Découvrez comment ajouter des bibliothèques Q # supplémentaires à vos applications Quantum.'
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
ms.openlocfilehash: b82113b925870d07c8a28aecd50176e009826062
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872620"
---
# <a name="using-additional-q-libraries"></a>Utilisation de bibliothèques Q # supplémentaires

Le kit de développement quantum fournit des fonctionnalités supplémentaires spécifiques au domaine via des _packages NuGet_ qui peuvent être ajoutés à vos projets Q #.

| Bibliothèque Q #  | Package NuGet | Remarques |
|---------|---------|--------|
| [Bibliothèque standard Q #](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. Quantum. standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Incluse par défaut |
| [Bibliothèque de chimie de quantum](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Bibliothèque de valeurs numériques de quantum](xref:microsoft.quantum.numerics.intro) | [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Bibliothèque de Machine Learning quantique](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Une fois que vous avez installé le kit de développement Quantum pour une utilisation avec votre environnement et votre langue d’hôte préférés, vous pouvez facilement ajouter des bibliothèques à des projets Q # individuels sans aucune autre installation.

> [!NOTE]
> Certaines bibliothèques Q # peuvent fonctionner correctement avec des outils supplémentaires qui fonctionnent avec vos programmes Q #, ou qui s’intègrent à vos applications hôtes.
> Par exemple, les [instructions d’installation de la bibliothèque chimie](xref:microsoft.quantum.chemistry.concepts.installation) décrivent comment utiliser le [package **Microsoft. Quantum. chimie** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) avec la plateforme de calcul de la chimie NWChem et comment installer les `qdk-chem` outils en ligne de commande pour l’utilisation des données de la chimie quantique.

## <a name="q-command-line-applications-or-net-interopability"></a>[Q # applications en ligne de commande ou .NET Interop](#tab/tabid-csproj)

**Ligne de commande ou Visual Studio code :** En utilisant la ligne de commande seule ou dans Visual Studio Code, vous pouvez utiliser la `dotnet` commande pour ajouter une référence de package NuGet à votre projet.
Par exemple, pour ajouter le package [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , exécutez la commande suivante :

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio :** Si vous utilisez Visual Studio 2019 ou une version ultérieure, vous pouvez ajouter des packages Q # supplémentaires à l’aide du gestionnaire de package NuGet.
Pour charger un package : 
1. Avec un projet ouvert dans Visual Studio, sélectionnez **gérer les packages NuGet...** dans le menu **projet** .

2. Cliquez sur **Parcourir**, sélectionnez **inclure la version préliminaire** et recherchez le nom du package « Microsoft. Quantum. Numerics ». Cela permet de répertorier les packages disponibles au téléchargement.

3. Pointez sur **Microsoft. Quantum. Numerics** , puis cliquez sur la flèche pointant vers le bas à droite du numéro de version pour installer le package de valeurs numériques.

Pour plus d’informations, consultez le Guide de l' [interface utilisateur du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Vous pouvez également utiliser la console du gestionnaire de package pour ajouter la bibliothèque numérique à votre projet par le biais de l’interface de ligne de commande.

![Utiliser la console du gestionnaire de package à partir de la ligne de commande](~/media/vs2017-nuget-console-menu.png)

À partir de la console du gestionnaire de package, exécutez la commande suivante :

```
Install-Package Microsoft.Quantum.Numerics
```

Pour plus d’informations, consultez le Guide de la [console du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="iq-notebooks"></a>[Bloc-notes IQ #](#tab/tabid-notebook)

Vous pouvez rendre des packages supplémentaires disponibles pour une utilisation dans un bloc-notes IQ # à l’aide de la [ `%package` commande Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).
Par exemple, pour ajouter le package [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) à utiliser dans un bloc-notes IQ #, exécutez la commande suivante dans une cellule de bloc-notes :

```
%package Microsoft.Quantum.Numerics
```

Après cette commande, le package est disponible pour toutes les cellules dans le bloc-notes.
Pour rendre le package disponible à partir du code Q # dans l’espace de travail actuel, rechargez l’espace de travail après avoir ajouté votre package :

```
%workspace reload
```

## <a name="python-interoperability"></a>[Interopérabilité de Python](#tab/tabid-python)


Vous pouvez rendre des packages supplémentaires disponibles pour une utilisation dans un programme hôte Python à l’aide de la [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) méthode.
Par exemple, pour ajouter le package [**Microsoft. Quantum. Numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) à utiliser dans un bloc-notes IQ #, exécutez le code python suivant :

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Après cette commande, le package sera mis à la disposition de tout code Q # compilé à l’aide de `qsharp.compile` .
Pour rendre le package disponible à partir du code Q # dans l’espace de travail actuel, rechargez l’espace de travail après avoir ajouté votre package :

```python
qsharp.reload()
```

***
