---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Opération DrawRandomDouble
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192942"
---
# <a name="drawrandomdouble-operation"></a>Opération DrawRandomDouble

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dessine un nombre réel aléatoire dans un intervalle inclusif donné.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Entrée

### <a name="min--double"></a>min : [double](xref:microsoft.quantum.lang-ref.double)

Plus petit nombre réel à dessiner.


### <a name="max--double"></a>Max : [double](xref:microsoft.quantum.lang-ref.double)

Nombre réel le plus grand à dessiner.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Nombre réel aléatoire dans l’intervalle inclusif de `min` à `max` avec une probabilité uniforme.

## <a name="remarks"></a>Notes

Échoue si `max <= min` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)