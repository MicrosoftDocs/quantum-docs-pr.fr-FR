---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706443"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a>TimeDependentTrotterSimulationAlgorithm fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


`TimeDependentSimulationAlgorithm` fonction qui utilise une décomposition Trotter – Suzuki pour rapprocher un opérateur unitaire qui résout l’équation Schrodinger qui dépend du temps.

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a>Entrée

### <a name="trotterstepsize--double"></a>trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)

Durée de l’évolution de l’heure simulée dans une seule étape trotter.


### <a name="trotterorder--int"></a>trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)

Ordre de l’intégrateur trotter. Il doit s’agir de 1 ou d’un nombre pair.



## <a name="output--timedependentsimulationalgorithm"></a>Sortie : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

Type `TimeDependentSimulationAlgorithm`.