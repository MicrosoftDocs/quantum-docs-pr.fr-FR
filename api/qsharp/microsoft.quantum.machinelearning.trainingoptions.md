---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Type défini par l’utilisateur TrainingOptions
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842778"
---
# <a name="trainingoptions-user-defined-type"></a>Type défini par l’utilisateur TrainingOptions

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Collection d’options à utiliser pour l’apprentissage des classifieurs Quantum.

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Éléments nommés

### <a name="learningrate--double"></a>LearningRate : [double](xref:microsoft.quantum.lang-ref.double)

Taux d’apprentissage par lequel les dégradés doivent être mis à l’échelle lors de la mise à jour des paramètres de modèle pendant les étapes d’apprentissage.
### <a name="tolerance--double"></a>Tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance approximative à utiliser lors de la préparation des exemples en tant qu’États quantiques.
### <a name="minibatchsize--int"></a>MinibatchSize : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’échantillons à utiliser dans chaque minilot d’apprentissage.
### <a name="nmeasurements--int"></a>NMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où chaque résultat de la classification doit être mesuré afin d’estimer la probabilité de la classification.
### <a name="maxepochs--int"></a>MaxEpochs : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre maximal d’époques pour l’apprentissage de chaque modèle.
### <a name="maxstalls--int"></a>MaxStalls : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre maximal de fois où une époque d’apprentissage est autorisée à se bloquer (à peu près zéro gradient) avant d’échouer.
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor : [double](xref:microsoft.quantum.lang-ref.double)

Valeur de redimensionnement des modèles bloqués par avant une nouvelle tentative de mise à jour.
### <a name="scoringperiod--int"></a>ScoringPeriod : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’étapes de dégradé à effectuer entre les points de notation.
Pour une meilleure précision, définissez sur 1.
### <a name="verbosemessage--string---unit"></a>VerboseMessage : [](xref:microsoft.quantum.lang-ref.string) -> [unité](xref:microsoft.quantum.lang-ref.unit) de chaîne

Fonction qui peut être utilisée pour fournir des commentaires détaillés.

## <a name="remarks"></a>Notes

Ce type défini par l’utilisateur ne doit pas être créé directement, mais il doit être spécifié en appelant @"microsoft.quantum.machinelearning.defaulttrainingoptions" , puis en utilisant l' `w/` opérateur pour remplacer des valeurs par défaut différentes.

Par exemple, pour utiliser les mesures 100 000 et au plus 8 époques de formation :

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Références

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)