---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701236"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution fonction)

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Packages [](https://nuget.org/packages/)


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