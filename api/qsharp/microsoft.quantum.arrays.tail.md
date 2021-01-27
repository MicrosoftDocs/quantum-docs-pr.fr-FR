---
uid: Microsoft.Quantum.Arrays.Tail
title: fonction Tail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845410"
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