---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193078"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution fonction)

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne une distribution uniforme sur un intervalle inclusif donné.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrée

### <a name="min--double"></a>min : [double](xref:microsoft.quantum.lang-ref.double)

Plus petit nombre réel à dessiner.


### <a name="max--double"></a>Max : [double](xref:microsoft.quantum.lang-ref.double)

Nombre réel le plus grand à dessiner.



## <a name="output--continuousdistribution"></a>Sortie : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Distribution dont les variates aléatoires sont des nombres réels dans l’intervalle inclusif de `min` à `max` avec une probabilité uniforme.

## <a name="remarks"></a>Notes

Échoue si `max <= min` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)