---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Opération DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847620"
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

## <a name="example"></a>Exemple

L’extrait de code Q # suivant dessine aléatoirement un angle entre $0 $ et $2 \pi $ :

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>Notes

Échoue si `max <= min` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)