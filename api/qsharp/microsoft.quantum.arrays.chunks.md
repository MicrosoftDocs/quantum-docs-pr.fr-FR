---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segments, fonction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842877"
---
# <a name="chunks-function"></a>Segments, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fractionne un tableau en plusieurs parties de longueur égale.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Entrée

### <a name="nelements--int"></a>nElements : [entier](xref:microsoft.quantum.lang-ref.int)

Longueur de chaque segment.


### <a name="arr--t"></a>ARR : 't []

Tableau à fractionner.



## <a name="output--t"></a>Sortie : 't [] []

Tableau contenant chaque segment du tableau d’origine.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

Notez que le dernier élément de la sortie peut être plus petit que `nElements` si `Length(arr)` n’est pas divisible par `nElements` .