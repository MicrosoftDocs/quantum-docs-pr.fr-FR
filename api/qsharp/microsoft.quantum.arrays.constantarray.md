---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846219"
---
# <a name="constantarray-function"></a>ConstantArray fonction)

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crée un tableau de longueur donnée avec tous les éléments égaux à la valeur donnée.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Entrée

### <a name="length--int"></a>Longueur : [int](xref:microsoft.quantum.lang-ref.int)

Longueur du nouveau tableau.


### <a name="value--t"></a>valeur : 't

Valeur de chaque élément du nouveau tableau.



## <a name="output--t"></a>Sortie : 't []

Nouveau tableau de longueur `length` , de telle sorte que chaque élément est `value` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="example"></a>Exemple

Le code suivant crée un tableau de 3 valeurs booléennes, chacune d’elles étant égale à `true` :

```qsharp
let array = ConstantArray(3, true);
```