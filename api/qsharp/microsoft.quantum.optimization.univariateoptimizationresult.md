---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Type défini par l’utilisateur UnivariateOptimizationResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708789"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>Type défini par l’utilisateur UnivariateOptimizationResult

Espace de noms : [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Packages [](https://nuget.org/packages/)


Représente le résultat de l’optimisation d’une fonction Student.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Éléments nommés

### <a name="coordinate--double"></a>Coordonnée : [double](xref:microsoft.quantum.lang-ref.double)

Entrée à laquelle une optimale a été trouvée.
### <a name="value--double"></a>Valeur : [double](xref:microsoft.quantum.lang-ref.double)

Valeur retournée par la fonction à son niveau optimal.