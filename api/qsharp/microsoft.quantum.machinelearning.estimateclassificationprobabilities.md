---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Opération EstimateClassificationProbabilities
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211897"
---
# <a name="estimateclassificationprobabilities-operation"></a>Opération EstimateClassificationProbabilities

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Étant donné un ensemble d’exemples et un classifieur séquentiel, évalue la probabilité de classification pour ces exemples en mesurant de manière répétée la sortie du classifieur sur chaque échantillon.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Entrée

### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance à autoriser dans l’encodage de l’échantillon en une opération de préparation de l’État.


### <a name="model--sequentialmodel"></a>modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modèle séquentiel à utiliser pour estimer les probabilités de classification pour les exemples donnés.


### <a name="samples--double"></a>exemples : [double](xref:microsoft.quantum.lang-ref.double)[] []

Tableau de vecteurs de fonctionnalité pour chaque échantillon à classer.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de mesures à utiliser pour estimer la probabilité de classification.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau d’estimations de la probabilité de classification pour chaque échantillon donné.