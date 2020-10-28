---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702961"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray fonction)

Espace de noms : [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Packages [](https://nuget.org/packages/)


Produit une représentation binaire d’un entier positif, à l’aide de la représentation avec primauté des octets de poids faible (Little-endian) pour le tableau retourné.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Entrée

### <a name="number--int"></a>nombre : [entier](xref:microsoft.quantum.lang-ref.int)

Entier positif à convertir en tableau de valeurs booléennes.


### <a name="bits--int"></a>bits : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de bits dans la représentation binaire de `number` .



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tableau de valeurs booléennes représentant `number` .

## <a name="remarks"></a>Notes

L’entrée `bits` doit être comprise entre 0 et 63.
L’entrée `number` doit être comprise entre 0 et $2 ^ {\texttt{bits}}-$1.