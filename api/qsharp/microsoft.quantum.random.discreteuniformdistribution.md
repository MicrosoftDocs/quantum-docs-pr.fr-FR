---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706726"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution fonction)

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Packages [](https://nuget.org/packages/)


Retourne une distribution uniforme sur une plage inclusive donnée.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Entrée

### <a name="min--int"></a>min : [int](xref:microsoft.quantum.lang-ref.int)

Plus petit entier à dessiner.


### <a name="max--int"></a>Max : [entier](xref:microsoft.quantum.lang-ref.int)

Plus grand entier à dessiner.



## <a name="output--discretedistribution"></a>Sortie : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Une distribution dont les variates aléatoires sont des entiers dans la plage inclusive comprise entre `min` et `max` avec une probabilité uniforme.

## <a name="remarks"></a>Notes

Échoue si `max <= min` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)