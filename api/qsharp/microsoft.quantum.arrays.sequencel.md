---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Fonction Sequence
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850983"
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

## <a name="example"></a>Exemple

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>Notes

La différence entre `from` et `to` doit tenir dans une `Int` valeur.