---
title: Glossaire de la bibliothèque de Machine Learning Quantum
description: Glossaire des termes du Machine Learning Quantum
author: alexeib2
ms.author: alexeib
ms.date: 2/27/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: b6133c1f3068dff597f71d2111e5e117131a7fd1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852721"
---
# <a name="quantum-machine-learning-glossary"></a>Glossaire Machine Learning Quantum

La formation d’un classifieur Quantum centré sur les circuits est un processus avec de nombreuses pièces mobiles qui requièrent la même quantité d’étalonnage par essai et l’erreur de formation de classifieurs traditionnels. Ici, nous définissons les principaux concepts et ingrédients de ce processus d’apprentissage.

## <a name="trainingtesting-schedules"></a>Planifications de formation et de test

Dans le contexte de l’apprentissage du classifieur, une *planification* décrit un sous-ensemble d’exemples de données dans un jeu d’apprentissage ou de test global. Une planification est généralement définie en tant que collection d’index.

## <a name="parameterbias-scores"></a>Scores des paramètres/biais

Étant donné un vecteur de paramètre candidat et un décalage de classifieur, le *score de validation* est mesuré par rapport à une planification de validation choisie et est exprimé par un certain nombre de classifications incorrectes comptées sur tous les échantillons de la planification.

## <a name="hyperparameters"></a>Hyperparamètres

Le processus d’apprentissage du modèle est régi par certaines valeurs prédéfinies appelées *hyperparamètres*:

### <a name="learning-rate"></a>Taux d’apprentissage

Il s’agit de l’un des hyperparamètres de clé. Il définit la quantité d’estimations de gradient stochastique actuelle qui a un impact sur la mise à jour des paramètres. La taille du delta de mise à jour des paramètres est proportionnelle au taux d’apprentissage. Des taux d’apprentissage plus faibles conduisent à une évolution des paramètres plus lente et une convergence plus lente, mais les valeurs excessivement grandes de LR peuvent perturber complètement la convergence, car la descente de dégradé ne s’engage jamais sur une valeur minimale locale particulière. Tandis que le taux d’apprentissage est ajusté de manière adaptative par l’algorithme d’apprentissage dans une certaine mesure, il est important de sélectionner une bonne valeur initiale pour celle-ci. Une valeur initiale par défaut normale pour le taux d’apprentissage est 0,1. La sélection de la meilleure valeur du taux d’apprentissage est une fine illustration (voir, par exemple, la section 4,3 de Goodfellow et al., « Deep Learning », MIT Press, 2017).

### <a name="minibatch-size"></a>Taille de minilot

Définit le nombre d’échantillons de données utilisés pour une seule estimation du gradient stochastique. Des valeurs plus élevées de taille minilot entraînent généralement une convergence plus robuste et plus monotone, mais peuvent ralentir le processus d’apprentissage, car le coût d’une estimation de dégradé est proportionnel à la taille du minimatch. Une valeur par défaut normale pour la taille de minilot est 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Époques de formation, tolérance, gridlocks

« Époque » signifie qu’une passe complète est effectuée sur les données d’apprentissage planifiées.
Le nombre maximal d’époques par thread d’apprentissage (voir ci-dessous) doit être limité. Le thread d’apprentissage est défini pour s’arrêter (avec les meilleurs paramètres candidats connus) lorsque le nombre maximal d’époques a été atteint. Toutefois, cette formation se terminerait plus tôt lorsque la tarification incorrecte du calendrier de validation passe sous une tolérance choisie. Supposons, par exemple, que la tolérance de la classification incorrecte est de 0,01 (1%); si, dans le cas d’un jeu de validation d’exemples 2000, nous observons moins de 20 incorrections de classifications, le niveau de tolérance a été atteint. Un thread d’apprentissage se termine également prématurément si le score de validation du modèle candidat n’a pas montré d’amélioration par rapport à plusieurs époques consécutives (un Gridlock). La logique de l’arrêt de Gridlock est actuellement codée en dur.

### <a name="measurements-count"></a>Nombre de mesures

En estimant les scores de formation/validation et les composants du gradient stochastique sur un appareil quantique, vous devez estimer les chevauchements d’état quantique qui requièrent plusieurs mesures du observables approprié. Le nombre de mesures doit être mis à l’échelle comme $O (1/\ Epsilon ^ 2) $ où $ \epsilon $ est l’erreur d’estimation souhaitée.
En règle générale, le nombre de mesures initiales peut être approximativement de $1/\ mbox {Tolerance} ^ 2 $ (voir la définition de la tolérance dans le paragraphe précédent). Vous devez réviser le nombre de mesures vers le haut si la profondeur du dégradé semble trop irrégulière et que la convergence est trop difficile à atteindre.

### <a name="training-threads"></a>Threads d’apprentissage

La fonction de vraisemblance, qui est l’utilitaire de formation pour le classifieur, est très rarement convexe, ce qui signifie qu’elle a généralement une multitude de Optima locaux dans l’espace de paramètres qui peuvent varier considérablement selon la qualité. Étant donné que le processus SGD peut converger vers un seul optimal spécifique, il est important d’explorer plusieurs vecteurs de paramètres de démarrage. La pratique courante dans Machine Learning consiste à initialiser de tels vecteurs de démarrage de façon aléatoire. L' Q# API d’apprentissage accepte un tableau arbitraire de tels vecteurs de démarrage, mais le code sous-jacent les explore séquentiellement. Sur un ordinateur multicœur ou en fait sur une architecture informatique parallèle, il est recommandé d’effectuer plusieurs appels à l' Q# API de formation en parallèle avec différentes initialisations de paramètres entre les appels.

#### <a name="how-to-modify-the-hyperparameters"></a>Comment modifier les hyperparamètres

Dans la bibliothèque QML, la meilleure façon de modifier les hyperparamètres consiste à remplacer les valeurs par défaut de l’UDT [`TrainingOptions`](xref:Microsoft.Quantum.MachineLearning.TrainingOptions) . Pour ce faire, nous l’appelons avec la fonction [`DefaultTrainingOptions`](xref:Microsoft.Quantum.MachineLearning.DefaultTrainingOptions) et appliquons l’opérateur `w/` pour remplacer les valeurs par défaut. Par exemple, pour utiliser les mesures 100 000 et un taux d’apprentissage de 0,01 :

```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
```
