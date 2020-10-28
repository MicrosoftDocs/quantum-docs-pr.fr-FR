---
title: Concevoir votre propre classifieur avec QDK
description: Découvrez les concepts de base de la conception de modèles de circuits pour le classifieur de circuit quantique.
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 221479e616ff7a03c4ac20e0062125660314e95b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691163"
---
# <a name="design-your-own-classifier"></a>Concevoir votre propre classifieur

Dans ce guide, vous allez découvrir les concepts de base qui sous-tendent la conception de modèles de circuit pour le classifieur d’un circuit orienté Quantum.

Comme dans l’apprentissage profond classique, il n’existe aucune règle générale pour choisir une architecture spécifique. Selon le problème, certaines architectures fonctionnent mieux que d’autres. Toutefois, certains concepts peuvent être utiles lors de la conception du circuit :

- Un grand nombre de paramètres implique un modèle plus flexible, qui peut être adapté à la création de limites de classification compliquées, mais qui peuvent également être plus susceptibles d’être surajustés.

- La contangation des portes entre les qubits est essentielle pour capturer les corrélations entre les fonctionnalités de Quantum.

## <a name="how-to-build-a-classifier-with-q"></a>Comment créer un classifieur avec Q\#

Pour créer un classifieur, nous allons concaténer des rotations contrôlées par paramétrée dans notre modèle de circuit. Pour ce faire, nous pouvons utiliser le type [`ControlledRotation`](xref:Microsoft.Quantum.MachineLearning.ControlledRotation) défini dans la bibliothèque de machine learning Quantum. Ce type accepte quatre arguments qui déterminent : l’index du qubit cible, le tableau des index du qubits de contrôle, l’axe de rotation et l’index du paramètre associé dans le tableau des paramètres définissant le modèle.

Voyons un exemple de classifieur. Dans l' [exemple de demi-lunes](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons), nous pouvons trouver le classifieur suivant défini dans le fichier `Training.qs` .

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

Nous définissons ici une fonction qui retourne un tableau d' `ControlledRotation` éléments, ainsi qu’un tableau de paramètres et un biais définit notre [`SequentialModel`](xref:Microsoft.Quantum.MachineLearning.SequentialModel) . Ce type est fondamental dans la bibliothèque de Machine Learning Quantum et définit le classifieur. Le circuit défini dans la fonction ci-dessus fait partie d’un classifieur dans lequel chaque échantillon du jeu de données contient deux fonctionnalités. Par conséquent, nous avons uniquement besoin de deux qubits. La représentation graphique du circuit est la suivante :

 ![Exemple de modèle de circuit](~/media/circuit_model_1.PNG)

Notez que, par défaut, les opérations de la bibliothèque de Machine Learning Quantum mesurent le dernier qubit du Registre pour estimer les probabilités de classification. Vous devez garder à l’esprit ce fait lors de la conception de votre circuit.

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Utiliser les fonctions de bibliothèque pour écrire des couches de portes

Supposons que nous disposons d’un jeu de données avec 784 fonctionnalités par instance, par exemple des images de 28 × 28 pixels, comme le jeu de données MNIST. Dans ce cas, la largeur du circuit est suffisamment grande pour permettre l’écriture à la main chaque porte individuelle devient une tâche possible mais difficile. C’est pourquoi la bibliothèque Quantum Machine Learning fournit un ensemble d’outils permettant de générer automatiquement des couches de rotations paramétrée. Par exemple, la fonction [`LocalRotationsLayer`](xref:Microsoft.Quantum.MachineLearning.LocalRotationsLayer) retourne un tableau de rotations uniqubit non contrôlées sur un axe donné, avec une rotation pour chaque qubit du Registre, chaque paramétrée par un paramètre de modèle différent. Par exemple, `LocalRotationsLayer(4, X)` retourne le jeu de portes suivant :

 ![Couche de rotations locales](~/media/local_rotations_layer.PNG)

Nous vous recommandons d’explorer les informations [de référence sur l’API de la bibliothèque de machine learning Quantum](xref:Microsoft.Quantum.MachineLearning) pour découvrir tous les outils disponibles pour rationaliser la conception du circuit.

## <a name="next-steps"></a>Étapes suivantes

 Essayez différentes structures dans les exemples fournis par les exemples. Des modifications ont-elles été apportées aux performances du modèle ? Dans le didacticiel suivant, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) , vous apprendrez à charger des jeux de données pour essayer d’explorer de nouvelles architectures de classifieurs.
