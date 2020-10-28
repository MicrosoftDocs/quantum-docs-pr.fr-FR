---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Opération EstimateClassificationProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701383"
---
# <a name="estimateclassificationprobability-operation"></a>Opération EstimateClassificationProbability

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Étant donné un échantillon et un classifieur séquentiel, évalue la probabilité de classification pour cet échantillon en mesurant de manière répétée la sortie du classifieur sur l’échantillon donné.

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>Entrée

### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance à autoriser dans l’encodage de l’échantillon en une opération de préparation de l’État.


### <a name="model--sequentialmodel"></a>modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modèle séquentiel à utiliser pour estimer la probabilité de classification pour l’échantillon donné.


### <a name="sample--double"></a>exemple : [double](xref:microsoft.quantum.lang-ref.double)[]

Vecteur de fonctionnalité de l’exemple à classer.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de mesures à utiliser pour estimer la probabilité de classification.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Estimation de la probabilité de classification pour l’échantillon donné.