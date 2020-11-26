---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Fonction Sequence
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220261"
---
# <a name="sequencel-function"></a>Fonction Sequence

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Obtient un tableau d’entiers dans un intervalle donné.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Entrée

### <a name="from--bigint"></a>de : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Index de début inclusif de l’intervalle.


### <a name="to--bigint"></a>à : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Index de fin inclusif de l’intervalle qui n’est pas inférieur à `from` .



## <a name="output--bigint"></a>Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)[]

Tableau contenant la séquence de nombres `from` , `from + 1` ,..., `to` .

## <a name="remarks"></a>Notes

La différence entre `from` et `to` doit tenir dans une `Int` valeur.