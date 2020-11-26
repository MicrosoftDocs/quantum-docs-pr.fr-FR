---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Séquencei, fonction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220295"
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