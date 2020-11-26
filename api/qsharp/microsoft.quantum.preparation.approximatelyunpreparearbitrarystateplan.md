---
uid: Microsoft.Quantum.Preparation.ApproximatelyUnprepareArbitraryStatePlan
title: ApproximatelyUnprepareArbitraryStatePlan fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: 2aab8b7a21ded729e90695c82709901bfacc18e7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226500"
---
# <a name="approximatelyunpreparearbitrarystateplan-function"></a>ApproximatelyUnprepareArbitraryStatePlan fonction)

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Étape d’implémentation de la procédure de préparation de l’état arbitraire.

```qsharp
function ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a>Entrée

### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)




### <a name="coefficients--complexpolar"></a>coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="rngcontrol--range"></a>rngControl : [plage](xref:microsoft.quantum.lang-ref.range)




### <a name="idxtarget--int"></a>idxTarget : [entier](xref:microsoft.quantum.lang-ref.int)





## <a name="output--qubit--unit--is-adj--ctl"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL []



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. PrepareArbitraryState](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [Microsoft. Quantum. Canon. MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)