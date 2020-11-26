---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196359"
---
# <a name="inferredlabels-function"></a>InferredLabels fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Étant donné un tableau de probabilités de classification et un décalage, retourne l’étiquette déduite de chaque probabilité.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Entrée

### <a name="bias--double"></a>biais : [double](xref:microsoft.quantum.lang-ref.double)

Le décalage entre deux classes, généralement le résultat de l’apprentissage d’un classifieur.


### <a name="probabilities--double"></a>probabilités : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau des probabilités de classification pour un ensemble d’exemples, en général résultant de l’estimation des fréquences de classification.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]

Étiquette déduite à partir de chaque probabilité de classification.