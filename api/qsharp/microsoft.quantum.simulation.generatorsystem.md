---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Type défini par l’utilisateur GeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708891"
---
# <a name="generatorsystem-user-defined-type"></a>Type défini par l’utilisateur GeneratorSystem

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Représente une collection de `GeneratorIndex` es.

Nous effectuons une itération sur cette collection à l’aide d’un entier à index unique, et la taille de la collection est supposée être connue.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Notes

Les instances de `GeneratorSystem` peuvent être définies facilement à l’aide de la <xref:microsoft.quantum.arrays.lookupfunction> fonction.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)