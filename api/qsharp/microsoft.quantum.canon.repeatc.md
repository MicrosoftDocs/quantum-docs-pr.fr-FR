---
uid: Microsoft.Quantum.Canon.RepeatC
title: Opération RepeatC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 30fd172584b36601c4b81deff494cf55964518f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205437"
---
# <a name="repeatc-operation"></a>Opération RepeatC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Répète une opération un nombre de fois donné.

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a>Entrée

### <a name="op--tinput--unit--is-ctl"></a>OP : 'TInput => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL

Opération à appeler à plusieurs reprises.


### <a name="ntimes--int"></a>nTimes : [int](xref:microsoft.quantum.lang-ref.int)

Nombre d’appels de `op` .


### <a name="input--tinput"></a>entrée : 'TInput

Entrée à passer à `op` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="tinput"></a>'TInput



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. Quantum. Canon. Repeata](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. Quantum. Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)