---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833301"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray fonction)

Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Produit une représentation binaire d’un entier non négatif, à l’aide de la représentation avec primauté des octets de poids faible (Little-endian) pour le tableau retourné.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Entrée

### <a name="number--int"></a>nombre : [entier](xref:microsoft.quantum.lang-ref.int)

Entier non négatif à convertir en tableau de valeurs booléennes.


### <a name="bits--int"></a>bits : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de bits dans la représentation binaire de `number` .



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tableau de valeurs booléennes représentant `number` .

## <a name="remarks"></a>Notes

L’entrée `bits` doit être comprise entre 0 et 63.
L’entrée `number` doit être comprise entre 0 et $2 ^ {\texttt{bits}}-$1.