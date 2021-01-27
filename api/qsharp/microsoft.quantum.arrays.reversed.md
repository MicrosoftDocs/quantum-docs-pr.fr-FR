---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fonction inversée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845453"
---
# <a name="reversed-function"></a>Fonction inversée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Créez un tableau qui contient les mêmes éléments qu’un tableau d’entrée, mais dans l’ordre inverse.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="array--t"></a>Tableau : 't []

Tableau dont les éléments doivent être copiés dans l’ordre inverse.



## <a name="output--t"></a>Sortie : 't []

Tableau contenant les éléments `array[Length(array) - 1]` .. `array[0]`.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type des éléments du tableau.