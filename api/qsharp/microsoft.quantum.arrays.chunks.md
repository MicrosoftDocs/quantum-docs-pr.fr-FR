---
uid: Microsoft.Quantum.Arrays.Chunks
title: Segments, fonction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706174"
---
# <a name="chunks-function"></a>Segments, fonction

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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