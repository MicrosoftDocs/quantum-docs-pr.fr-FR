---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204689"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule la taille de l’étape trotter dans l’implémentation récursive de l’algorithme de simulation trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Entrée

### <a name="order--int"></a>commande : [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Notes

Cette opération utilise une convention d’indexation différente de celle de [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). En particulier, `DecomposedIntoTimeStepsCA(_, 4)` correspond au scalaire $p _2 (\lambda) $ dans quant-pH/0508139.