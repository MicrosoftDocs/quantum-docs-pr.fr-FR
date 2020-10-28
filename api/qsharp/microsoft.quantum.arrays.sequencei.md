---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Séquencei, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705795"
---
# <a name="sequencei-function"></a>Séquencei, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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