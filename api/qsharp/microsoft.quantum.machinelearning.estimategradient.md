---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Opération EstimateGradient
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 79f4abdf131509d4948a3c114e631118329f88d8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211846"
---
# <a name="estimategradient-operation"></a>Opération EstimateGradient

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Estime le dégradé d’apprentissage pour un classifieur séquentiel au niveau d’un modèle particulier et pour une entrée encodée donnée.

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>Entrée

### <a name="model--sequentialmodel"></a>modèle : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Modèle séquentiel dont le dégradé doit être estimé.


### <a name="encodedinput--stategenerator"></a>encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Entrée du classifieur séquentiel, encodée en une opération de préparation de l’État.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de mesures à utiliser pour estimer le dégradé.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]

Estimation du dégradé d’apprentissage aux paramètres d’entrée et de modèle donnés.

## <a name="remarks"></a>Notes

Cette opération utilise un test Hadarmard et la technique de changement de paramètre ensemble pour estimer le dégradé.