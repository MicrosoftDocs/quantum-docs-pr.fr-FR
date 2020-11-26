---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 141edf6e425a060a995bfc181aefb1bcffdb128b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196699"
---
# <a name="_updatedbias-function"></a>_UpdatedBias fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Retourne une valeur de biais qui génère un score de classification incorrecte presque minimal.

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>Entrée

### <a name="labeledprobabilities--doubleint"></a>labeledProbabilities : ([double](xref:microsoft.quantum.lang-ref.double),[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="bias--double"></a>biais : [double](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

