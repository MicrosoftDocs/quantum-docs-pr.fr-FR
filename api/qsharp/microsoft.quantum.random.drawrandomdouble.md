---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Opération DrawRandomDouble
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708645"
---
# <a name="drawrandomdouble-operation"></a>Opération DrawRandomDouble

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Packages [](https://nuget.org/packages/)


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