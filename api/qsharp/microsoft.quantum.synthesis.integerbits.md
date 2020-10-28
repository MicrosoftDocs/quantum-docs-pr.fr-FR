---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706427"
---
# <a name="integerbits-function"></a>IntegerBits fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)


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