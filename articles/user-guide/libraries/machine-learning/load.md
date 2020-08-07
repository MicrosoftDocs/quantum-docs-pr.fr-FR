---
title: Chargement de données classiques
description: Découvrez comment charger votre propre jeu de données pour former un modèle de classifieur avec l’Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 26ba7411c9ade1d6c4b606e8c12c10ade18fc584
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868829"
---
# <a name="load-and-classify-your-own-datasets"></a>Charger et classer vos propres jeux de données

Dans ce bref didacticiel, nous allons apprendre à charger votre propre jeu de données pour former un modèle de classifieur avec le kit de développement quantique (QDK).

Nous vous recommandons vivement d’utiliser un format de sérialisation standardisé, tel que les [fichiers JSON](https://en.wikipedia.org/wiki/JSON) , pour stocker vos données.
Ces formats offrent une haute compatibilité avec différents frameworks comme Python et l’écosystème .NET.
En particulier, nous vous recommandons d’utiliser notre modèle pour le chargement des données, afin que vous puissiez copier-coller le code directement à partir des exemples.

## <a name="template-for-loading-your-datasets"></a>Modèle pour le chargement de vos jeux de données

Supposons que nous disposons d’un jeu de données d’apprentissage $ (x, y) $ de taille $N = $2 où chaque instance $x _i $ de $x $ a trois fonctionnalités : $x _ {I1} $, $x _ {I2} $ et $x _ {i3} $.
Le DataSet de validation a la même structure.
Ces jeux peuvent être représentés par un `data.json` fichier similaire à ce qui suit :

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Exemple utilisant le modèle

Supposons que nous ayons un petit jeu de données avec des hauteurs et des poids de différents chats et chiens. Ce jeu de données est très petit pour effectuer l’apprentissage d’un modèle, mais il sera suffisant pour montrer le processus de chargement d’un jeu de données.

| Hauteur (m) | Poids (kg) | Animal |
|-----------|------------|--------|
| 0,54      | 30         | Dog    |
| 0.30      | 8          | Chats    |
| 0,91      | 44         | Dog    |
| 0.86      | 31          | Dog    |
| 0.32      | 5         | Chats    |
| 0,25      | 4          | Chats    |

Le processus est le suivant :

- Tout d’abord, nous devons séparer le jeu de données en formation et validation. Dans ce cas, nous pouvons simplement prendre les trois premiers exemples pour la formation et le reste des exemples à des fins de validation. En général, il est recommandé d’échantillonner de façon aléatoire le jeu de données de formation et de validation pour éviter les écarts indésirables dans les données d’apprentissage.
- Deuxièmement, nous devons attribuer une étiquette numérique à chaque classe. Notez que, pour le moment, la bibliothèque QML admet uniquement les problèmes de classification binaire. Nous allons donc attribuer l’étiquette 0 à la classe `Dog` et le numéro 1 à la classe `Cat` .
- Enfin, nous remplissons le modèle à l’aide des données de notre jeu de données. Notez que pour les jeux de données volumineux, vous devez générer un petit script pour générer automatiquement le modèle à partir de votre jeu de données spécifique. Ce script dépend du format d’origine de votre jeu de données.

Pour notre jeu de données, le `data.json` fichier est :

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Chargement des données

Une fois que vos données sont sérialisées sous la forme d’un fichier JSON, vous pouvez les charger dans à l’aide des bibliothèques JSON fournies avec le langage hôte de votre choix.

### <a name="python"></a>[Python](#tab/tabid-python)

Python fournit le [ `json` package intégré](https://docs.python.org/3.7/library/json.html) pour l’utilisation de données sérialisées JSON :

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

La plateforme .NET Core fournit le [ `System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) pour l’utilisation de données sérialisées JSON :

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Étapes suivantes

Vous êtes maintenant prêt à commencer à exécuter vos propres expériences avec vos propres jeux de données. Essayez différents classifieurs et jeux de données et contribuez à la communauté partageant vos résultats.
