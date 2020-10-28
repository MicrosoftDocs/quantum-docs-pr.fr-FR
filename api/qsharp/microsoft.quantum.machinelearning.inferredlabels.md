---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708000"
---
# <a name="inferredlabels-function"></a>InferredLabels fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


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