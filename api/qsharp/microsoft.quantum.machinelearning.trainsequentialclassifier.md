---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Opération TrainSequentialClassifier
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: d0b0587ffa93141739bcd6f39324571ffc28dacc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228659"
---
# <a name="trainsequentialclassifier-operation"></a>Opération TrainSequentialClassifier

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Étant donné la structure d’un classifieur séquentiel, forme le classifieur sur un jeu d’apprentissage étiqueté donné.

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Entrée

### <a name="models--sequentialmodel"></a>modèles : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]

Tableau de modèles à utiliser comme points de départ pendant l’apprentissage.


### <a name="samples--labeledsample"></a>exemples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Ensemble de données d’apprentissage étiquetées qui seront utilisées pour effectuer l’apprentissage.


### <a name="options--trainingoptions"></a>Options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Configuration à utiliser lors de la formation ; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" pour plus d’informations, consultez et.


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Une planification d’échantillonnage à utiliser lors de la sélection d’exemples à partir des données d’apprentissage pendant les étapes de formation.


### <a name="validationschedule--samplingschedule"></a>validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Une planification d’échantillonnage à utiliser lors de la sélection d’exemples à partir des données d’apprentissage lors de la sélection du point de départ qui a entraîné le meilleur score de classifieur.



## <a name="output--sequentialmodelint"></a>Sortie : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))

- Paramétrage du classifieur donné et d’un décalage entre les deux classes, qui correspond au meilleur résultat de chacun des points de départ donnés.
- Nombre d’échecs observés au meilleur modèle de classifieur.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. MachineLearning. TrainSequentialClassifierAtModel](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)