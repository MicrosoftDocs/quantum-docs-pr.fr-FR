---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: Opération de _RunSingleTrainingEpoch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: a8ae35fdd6c4e219444e7d6f7587ea31603b9999
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856182"
---
# <a name="_runsingletrainingepoch-operation"></a>Opération de _RunSingleTrainingEpoch

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Effectuez une époque de formation de classifieur séquentiel sur un sous-ensemble d’exemples de données.

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>Entrée

### <a name="encodedsamples--labeledsamplestategenerator"></a>encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []




### <a name="schedule--samplingschedule"></a>planification : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’étapes de dégradé à effectuer entre les points de notation.
Pour une meilleure précision, définissez sur 1.


### <a name="options--trainingoptions"></a>Options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Options à utiliser pour l’apprentissage.


### <a name="model--sequentialmodel"></a>modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modèle séquentiel à former.


### <a name="npreviousbestmisses--int"></a>nPreviousBestMisses : [entier](xref:microsoft.quantum.lang-ref.int)

Le meilleur nombre de classifications incorrectes observées dans les époques précédentes.



## <a name="output--intsequentialmodel"></a>Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))

- Plus petit nombre de classifications incorrectes observées par le biais de cette époque.
- Le nouveau modèle séquentiel le plus approprié a été trouvé.