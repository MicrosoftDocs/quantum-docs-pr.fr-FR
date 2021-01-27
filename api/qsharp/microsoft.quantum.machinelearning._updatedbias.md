---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 41a51d8a6a8af299ce3e84b727336b098a3d1160
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844446"
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

