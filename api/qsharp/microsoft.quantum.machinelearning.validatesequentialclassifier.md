---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: Opération ValidateSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706827"
---
# <a name="validatesequentialclassifier-operation"></a>Opération ValidateSequentialClassifier

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Valide un classifieur séquentiel donné par rapport à un ensemble donné d’exemples préétiquetés.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Entrée

### <a name="model--sequentialmodel"></a>modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modèle séquentiel à valider.


### <a name="samples--labeledsample"></a>exemples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Exemples à utiliser pour valider le modèle donné.


### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance approximative à utiliser pour l’encodage de chaque échantillon comme entrée du classifieur séquentiel.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de mesures à utiliser pour classer chaque échantillon.


### <a name="validationschedule--samplingschedule"></a>validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Planification selon laquelle les exemples doivent être dessinés à partir du jeu de validation.



## <a name="output--validationresults"></a>Sortie : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

Résultats de la validation donnée.