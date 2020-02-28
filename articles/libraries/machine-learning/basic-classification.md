---
title: Classification de base avec la bibliothèque de Machine Learning Quantum
description: 'Découvrez comment exécuter un classifieur séquentiel Quantum écrit en Q # à l’aide de la bibliothèque Quantum Machine Learning de Microsoft QDK.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: f42e3e4492f934d7a8f03d4fec6fa0de765401d7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909923"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Classification de base : classer les données avec QDK

Dans ce guide de démarrage rapide, vous allez apprendre à exécuter un classifieur séquentiel Quantum écrit en Q # à l’aide de la bibliothèque Quantum Machine Learning de QDK. 

Dans ce guide, nous allons utiliser le jeu de données de la demi-lune, à l’aide d’une structure de classifieur définie dans Q #.

## <a name="prerequisites"></a>Conditions préalables requises

- Le Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Créer un projet Q#](xref:microsoft.quantum.howto.createproject)

## <a name="host-program"></a>Programme hôte

Votre programme hôte se compose de trois parties :

- Chargez le jeu de données et choisissez un ensemble de paramètres de démarrage pour votre modèle.
- Exécutez la formation pour déterminer les paramètres et l’écart du modèle.
- Valider le modèle pour déterminer sa précision

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python avec Visual Studio Code ou la ligne de commande](#tab/tabid-python)

    Pour exécuter vous êtes le classificateur Q # de Python, enregistrez le code suivant en tant que `host.py`. N’oubliez pas que vous avez également besoin de la `Training.qs` de fichiers Q # qui est expliquée plus loin dans ce didacticiel.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Vous pouvez ensuite exécuter votre programme hôte Python à partir de la ligne de commande :

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# avec Visual Studio Code ou la ligne de commande](#tab/tabid-csharp)

    Pour exécuter vous êtes le classificateur Q # de C#, enregistrez le code suivant en tant que `Host.cs`. N’oubliez pas que vous avez également besoin de la `Training.qs` de fichiers Q # qui est expliquée plus loin dans ce didacticiel.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Vous pouvez ensuite exécuter votre programme hôte C# à partir de la ligne de commande :

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# avec Visual Studio 2019](#tab/tabid-vs2019)

    Pour exécuter votre nouveau programme Q # à C# partir de Visual Studio, modifiez `Host.cs` pour inclure le C# code suivant. N’oubliez pas que vous avez également besoin de la `Training.qs` de fichiers Q # qui est expliquée plus loin dans ce didacticiel.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Appuyez ensuite sur F5, le programme démarre l’exécution et une nouvelle fenêtre s’affiche avec les résultats suivants : 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q\# le code de classifieur

Voyons maintenant comment les opérations appelées par le programme hôte sont définies dans Q #.
Nous enregistrons le code suivant dans un fichier nommé `Training.qs`.

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Les fonctions et opérations les plus importantes définies dans le code ci-dessus sont les suivantes :

- `ClassifierStructure() : ControlledRotation[]` : dans cette fonction, nous définissons la structure de notre modèle de circuit en ajoutant les couches des portes contrôlées que nous considérons. Cette étape est analogue à la déclaration des couches de neurones dans un modèle d’apprentissage profond séquentiel.
- `TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)` : cette opération est la partie fondamentale du code et définit l’apprentissage. Ici, nous chargeons les exemples à partir du jeu de données inclus dans la bibliothèque, nous définissons les hyper paramètres et les paramètres initiaux pour l’apprentissage et nous commençons la formation en appelant l’opération `TrainSequentialClassifier` incluse dans la bibliothèque. Il génère les paramètres et le biais qui déterminent le classifieur.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : cette opération définit le processus de validation pour évaluer le modèle. Ici, nous chargeons les exemples pour la validation, le nombre de mesures par échantillon et la tolérance. Il génère le nombre de déclassifications incorrectes sur le lot d’exemples choisi à des fins de validation.

## <a name="next-steps"></a>Étapes suivantes

Tout d’abord, vous pouvez lire le code et essayer de modifier certains paramètres pour voir comment il affecte l’apprentissage. Ensuite, dans le didacticiel suivant, [Concevez votre propre classifieur](xref:microsoft.quantum.libraries.machine-learning.design), vous apprendrez à définir la structure du classifieur.
