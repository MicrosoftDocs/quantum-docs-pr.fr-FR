---
title: Classification de base avec la bibliothèque de Machine Learning Quantum
description: Découvrez comment exécuter un classificateur séquentiel Quantum écrit dans Q# à l’aide de la bibliothèque quantum machine learning de Microsoft QDK.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fe686a87fbdc610badc0bbcbc0bf7b065e0bce9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854043"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Classification de base : classer les données avec QDK

Dans ce guide de démarrage rapide, vous allez apprendre à exécuter un classificateur séquentiel Quantum écrit dans Q# à l’aide de la bibliothèque quantum machine learning de QDK. 

Dans ce guide, nous allons utiliser le jeu de données de la demi-lune, à l’aide d’une structure de classifieur définie dans Q# .

## <a name="prerequisites"></a>Prérequis

- Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Créez un Q# projet pour un [programme hôte python](xref:microsoft.quantum.install.python) ou un [programme hôte C#](xref:microsoft.quantum.install.cs).

## <a name="host-program"></a>Programme hôte

Votre programme hôte se compose de trois parties :

- Chargez le jeu de données et choisissez un ensemble de paramètres de démarrage pour votre modèle.
- Exécutez la formation pour déterminer les paramètres et l’écart du modèle.
- Valider le modèle pour déterminer sa précision

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python avec Visual Studio Code ou la ligne de commande](#tab/tabid-python)

    Pour exécuter vous êtes le Q# classifieur de Python, enregistrez le code suivant sous `host.py` . N’oubliez pas que vous avez également besoin du Q# fichier `Training.qs` qui est expliqué plus loin dans ce didacticiel.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# avec Visual Studio Code ou la ligne de commande](#tab/tabid-csharp)

    Pour exécuter vous êtes le Q# classifieur de C#, enregistrez le code suivant sous `Host.cs` . N’oubliez pas que vous avez également besoin du Q# fichier `Training.qs` qui est expliqué plus loin dans ce didacticiel.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande :

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# avec Visual Studio 2019](#tab/tabid-vs2019)

    Pour exécuter votre nouveau Q# programme à partir de C# dans Visual Studio, modifiez `Host.cs` pour inclure le code C# suivant. N’oubliez pas que vous avez également besoin du Q# fichier `Training.qs` qui est expliqué plus loin dans ce didacticiel.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Appuyez sur F5 pour que le programme commence à s’exécuter. Une nouvelle fenêtre affiche les résultats suivants : 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>\#Code du classifieur Q

Voyons maintenant comment les opérations appelées par le programme hôte sont définies dans Q# .
Nous enregistrons le code suivant dans un fichier nommé `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Les fonctions et opérations les plus importantes définies dans le code ci-dessus sont les suivantes :

- `ClassifierStructure() : ControlledRotation[]` : dans cette fonction, nous définissons la structure de notre modèle de circuit en ajoutant les couches des portes contrôlées que nous considérons. Cette étape est analogue à la déclaration des couches de neurones dans un modèle d’apprentissage profond séquentiel.
- `TrainHalfMoonModel() : (Double[], Double)` : cette opération est la partie fondamentale du code et définit l’apprentissage. Ici, nous chargeons les exemples à partir du jeu de données inclus dans la bibliothèque, nous définissons les hyper paramètres et les paramètres initiaux pour l’apprentissage et nous commençons l’apprentissage en appelant l’opération `TrainSequentialClassifier` incluse dans la bibliothèque. Il génère les paramètres et le biais qui déterminent le classifieur.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : cette opération définit le processus de validation pour évaluer le modèle. Ici, nous chargeons les exemples pour la validation, le nombre de mesures par échantillon et la tolérance. Il génère le nombre de déclassifications incorrectes sur le lot d’exemples choisi à des fins de validation.

## <a name="next-steps"></a>Étapes suivantes

Tout d’abord, vous pouvez lire le code et essayer de modifier certains paramètres pour voir comment il affecte l’apprentissage. Ensuite, dans le didacticiel suivant, [Concevez votre propre classifieur](xref:microsoft.quantum.libraries.machine-learning.design), vous apprendrez à définir la structure du classifieur.
