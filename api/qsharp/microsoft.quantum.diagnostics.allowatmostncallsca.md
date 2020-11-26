---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Opération AllowAtMostNCallsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202564"
---
# <a name="allowatmostncallsca-operation"></a>Opération AllowAtMostNCallsCA

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Entre un appel à cette opération et son voisin, déclare qu’une opération donnée est appelée au plus un certain nombre de fois.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a>Entrée

### <a name="ntimes--int"></a>nTimes : [int](xref:microsoft.quantum.lang-ref.int)

Nombre maximal de fois où `op` peut être appelé.


### <a name="op--tinput--toutput--is-adj--ctl"></a>OP : 'TInput => 'TOutput est Adj + CTL

Opération dont les appels doivent être restreints.


### <a name="message--string"></a>message : [chaîne](xref:microsoft.quantum.lang-ref.string)

Message à afficher en cas d’échec.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>«TOutput



## <a name="remarks"></a>Notes

Cette opération peut être remplacée par une absence d’opération sur les cibles qui ne la prennent pas en charge.