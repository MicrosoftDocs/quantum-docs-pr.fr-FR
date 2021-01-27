---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Séquencei, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3cf09e48cce1aeb1aac837465ee3a5e06adf5169
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851009"
---
# <a name="sequencei-function"></a>Séquencei, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Obtient un tableau d’entiers dans un intervalle donné.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Entrée

### <a name="from--int"></a>à partir de : [int](xref:microsoft.quantum.lang-ref.int)

Index de début inclusif de l’intervalle.


### <a name="to--int"></a>à : [int](xref:microsoft.quantum.lang-ref.int)

Index de fin inclusif de l’intervalle qui n’est pas inférieur à `from` .



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau contenant la séquence de nombres `from` , `from + 1` ,..., `to` .

## <a name="example"></a>Exemple

```qsharp
let arr1 = SequenceI(0, 3); // [0, 1, 2, 3]
let arr2 = SequenceI(23, 29); // [23, 24, 25, 26, 27, 28, 29]
let arr3 = SequenceI(-5, -2); // [-5, -4, -3, -2]

let numbers = SequenceI(0, _); // function to create sequence from 0 to `to`
let naturals = SequenceI(1, _); // function to create sequence from 1 to `to`
```