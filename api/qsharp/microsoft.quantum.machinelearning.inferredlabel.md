---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708015"
---
# <a name="inferredlabel-function"></a>InferredLabel fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


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