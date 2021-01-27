---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Type défini par l’utilisateur UnivariateOptimizationResult
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854567"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>Type défini par l’utilisateur UnivariateOptimizationResult

Espace de noms : [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente le résultat de l’optimisation d’une fonction Student.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Éléments nommés

### <a name="coordinate--double"></a>Coordonnée : [double](xref:microsoft.quantum.lang-ref.double)

Entrée à laquelle une optimale a été trouvée.
### <a name="value--double"></a>Valeur : [double](xref:microsoft.quantum.lang-ref.double)

Valeur retournée par la fonction à son niveau optimal.