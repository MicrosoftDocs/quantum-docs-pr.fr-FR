---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211778"
---
# <a name="inferredlabel-function"></a>InferredLabel fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Étant donné un de probabilité de classification et un biais, retourne l’étiquette déduite de cette probabilité.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Entrée

### <a name="bias--double"></a>biais : [double](xref:microsoft.quantum.lang-ref.double)

Le décalage entre deux classes, généralement le résultat de l’apprentissage d’un classifieur.


### <a name="probability--double"></a>probabilité : [double](xref:microsoft.quantum.lang-ref.double)

Probabilités de classification pour un échantillon donné, en général résultant de l’estimation de sa fréquence de classification.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Étiquette déduite de la probabilité de classification donnée.