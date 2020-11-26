---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 1ca9580ba603db8fee40e008a7ea51cb7a04d7d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229220"
---
# <a name="interpolategeneratorsystemsimpl-function"></a>InterpolateGeneratorSystemsImpl fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Interpole de manière linéaire entre deux `GeneratorSystems` en fonction d’un paramètre de planification `s` compris entre 0 et 1 (inclus).

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrée

### <a name="schedule--double"></a>planification : [double](xref:microsoft.quantum.lang-ref.double)

Un paramètre de planification $s \Dans [0, 1] $.


### <a name="generatorsystemstart--generatorsystem"></a>generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Début `GeneratorSystem` .


### <a name="generatorsystemend--generatorsystem"></a>generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Fin `GeneratorSystem` .



## <a name="output--generatorsystem"></a>Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Représentant un système qui est la somme des systèmes de générateur d’entrée, avec la pondération $ (1-s) $ on `generatorSystemStart` et le poids $s $ on `generatorSystemEnd` .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. simulation. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)