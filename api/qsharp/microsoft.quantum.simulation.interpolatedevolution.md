---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701731"
---
# <a name="interpolatedevolution-function"></a>InterpolatedEvolution fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Effectue une interpolation entre deux générateurs avec une planification uniforme, en retournant une opération qui applique l’évolution simulée sous le générateur dépendant du temps à un registre qubit.

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="interpolationtime--double"></a>interpolationTime : [double](xref:microsoft.quantum.lang-ref.double)

Temps nécessaire pour effectuer l’interpolation.


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Générateur initial pour simuler l’évolution sous.


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Générateur final pour simuler l’évolution.


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm : [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

Algorithme de simulation dépendant du temps qui sera utilisé pour simuler l’évolution pendant la planification de l’interpolation uniforme.



## <a name="output--qubit--unit-adj--ctl"></a>Sortie : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL



## <a name="remarks"></a>Notes

Si le temps d’interpolation est choisi pour respecter les conditions adiabatic, cette fonction retourne une opération qui effectue la préparation de l’État adiabatic pour le générateur dynamique final.