---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229152"
---
# <a name="multiplygeneratorsystem-function"></a>MultiplyGeneratorSystem fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Multiplie le coefficient de tous les termes dans un `GeneratorSystem` .

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrée

### <a name="multiplier--double"></a>multiplicateur : [double](xref:microsoft.quantum.lang-ref.double)

Multiplicateur sur le coefficient.


### <a name="generatorsystem--generatorsystem"></a>generatorSystem : [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem` à multiplier.



## <a name="output--generatorsystem"></a>Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Représentant un système avec des coefficients d’un facteur `multiplier` plus grand.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. simulation. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)