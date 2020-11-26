---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Type défini par l’utilisateur UnivariateOptimizationResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194030"
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