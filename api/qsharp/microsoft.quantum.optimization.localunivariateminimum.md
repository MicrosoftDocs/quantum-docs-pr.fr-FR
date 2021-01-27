---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854613"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum fonction)

Espace de noms : [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne la valeur minimale locale pour une fonction Student sur un intervalle délimité, à l’aide d’une recherche d’intervalle d’or.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Entrée

### <a name="fn--double---double"></a>FN : [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)

Fonction Student à réduire.


### <a name="bounds--doubledouble"></a>limites : ([double](xref:microsoft.quantum.lang-ref.double),[double](xref:microsoft.quantum.lang-ref.double))

Intervalle dans lequel la valeur minimale locale doit être recherchée.


### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Précision de l’entrée de la fonction à tolérer.
La recherche des Optima locaux se poursuivra jusqu’à ce que la largeur de l’intervalle soit inférieure à celle de cette tolérance.



## <a name="output--univariateoptimizationresult"></a>Sortie : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

Optima local de la fonction donnée, situé dans les limites spécifiées.