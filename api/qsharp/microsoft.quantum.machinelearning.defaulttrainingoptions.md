---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856007"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Retourne un jeu d’options par défaut pour les classifieurs d’apprentissage.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Sortie : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Un ensemble raisonnable d’options de formation par défaut à utiliser lors de l’apprentissage des classifieurs.

## <a name="example"></a>Exemple

Pour utiliser les options par défaut, mais avec des mesures supplémentaires, utilisez l' `w/` opérateur :

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```