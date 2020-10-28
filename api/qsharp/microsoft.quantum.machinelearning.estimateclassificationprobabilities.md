---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Opération EstimateClassificationProbabilities
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701389"
---
# <a name="estimateclassificationprobabilities-operation"></a>Opération EstimateClassificationProbabilities

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


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