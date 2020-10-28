---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Fonction incorrecte de classification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708471"
---
# <a name="misclassifications-function"></a>Fonction incorrecte de classification

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Étant donné un ensemble d’étiquettes déduites et un ensemble d’étiquettes correctes, retourne des index pour chaque ensemble d’étiquettes.

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>Entrée

### <a name="inferredlabels--int"></a>inferredLabels : [int](xref:microsoft.quantum.lang-ref.int)[]

Étiquettes déduites pour un ensemble d’apprentissage ou un jeu de validation donné.


### <a name="actuallabels--int"></a>actualLabels : [int](xref:microsoft.quantum.lang-ref.int)[]

Étiquettes vraies pour un ensemble d’apprentissage ou un jeu de validation donné.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau d’index de ce `idx` type `inferredLabels[idx] != actualLabels[idx]` .