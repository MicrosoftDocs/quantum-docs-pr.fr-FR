---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Type défini par l’utilisateur GeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225225"
---
# <a name="generatorsystem-user-defined-type"></a>Type défini par l’utilisateur GeneratorSystem

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une collection de `GeneratorIndex` es.

Nous effectuons une itération sur cette collection à l’aide d’un entier à index unique, et la taille de la collection est supposée être connue.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Notes

Les instances de `GeneratorSystem` peuvent être définies facilement à l’aide de la <xref:microsoft.quantum.arrays.lookupfunction> fonction.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)