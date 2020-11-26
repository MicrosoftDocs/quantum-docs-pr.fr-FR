---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Opération DrawRandomInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192908"
---
# <a name="drawrandomint-operation"></a>Opération DrawRandomInt

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dessine un entier aléatoire dans une plage inclusive donnée.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Entrée

### <a name="min--int"></a>min : [int](xref:microsoft.quantum.lang-ref.int)

Plus petit entier à dessiner.


### <a name="max--int"></a>Max : [entier](xref:microsoft.quantum.lang-ref.int)

Plus grand entier à dessiner.



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Entier dans la plage inclusive comprise entre `min` et `max` avec une probabilité uniforme.

## <a name="remarks"></a>Notes

Échoue si `max <= min` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)