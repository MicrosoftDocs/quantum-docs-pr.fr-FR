---
uid: Microsoft.Quantum.Arrays.Merged
title: Fonction fusionnée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705870"
---
# <a name="merged-function"></a>Fonction fusionnée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


À partir de deux tableaux triés, retourne un tableau unique contenant les éléments des deux en ordre trié. Utilisé en interne par le tri de fusion.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="comparison--tt---bool"></a>Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>gauche : 't []




### <a name="right--t"></a>Right : 't []





## <a name="output--t"></a>Sortie : 't []



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

