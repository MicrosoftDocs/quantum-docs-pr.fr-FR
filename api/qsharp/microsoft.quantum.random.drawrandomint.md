---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Opération DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851139"
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

## <a name="example"></a>Exemple

L’extrait de code Q # suivant remplace de manière aléatoire un dé à six côtés :

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a>Notes

Échoue si `max <= min` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)