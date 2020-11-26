---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231090"
---
# <a name="integerbits-function"></a>IntegerBits fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne toutes les positions dans lesquelles les bits d’un entier sont définis.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Entrée

### <a name="value--int"></a>valeur : [int](xref:microsoft.quantum.lang-ref.int)

Nombre non négatif.


### <a name="length--int"></a>Longueur : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de bits dans l’expansion binaire de `value` .



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]

Tableau qui contient toutes les positions de bits (à partir de 0) qui sont égales à 1 dans l’expansion binaire de la prise `value` en compte de tous les bits jusqu’à la position `length - 1` .  Toutes les positions sont classées dans le tableau par position dans un ordre de croisement.