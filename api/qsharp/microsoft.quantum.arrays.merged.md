---
uid: Microsoft.Quantum.Arrays.Merged
title: Fonction fusionnée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845610"
---
# <a name="merged-function"></a>Fonction fusionnée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

