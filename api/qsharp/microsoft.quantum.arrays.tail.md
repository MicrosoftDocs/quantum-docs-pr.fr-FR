---
uid: Microsoft.Quantum.Arrays.Tail
title: fonction Tail
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220091"
---
# <a name="tail-function"></a>fonction Tail

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne le dernier élément du tableau.

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>Entrée

### <a name="array--a"></a>Tableau : 'A []

Tableau dont le dernier élément est pris. La longueur du tableau doit être au moins égale à 1.



## <a name="output--a"></a>Sortie : 'A

Dernier élément du tableau.

## <a name="type-parameters"></a>Paramètres de type

### <a name="a"></a>'A

Type des éléments du tableau.