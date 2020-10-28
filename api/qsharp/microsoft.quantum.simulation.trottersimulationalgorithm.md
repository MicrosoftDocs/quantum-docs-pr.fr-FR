---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706438"
---
# <a name="trottersimulationalgorithm-function"></a>TrotterSimulationAlgorithm fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


`SimulationAlgorithm` fonction qui utilise une décomposition Trotter – Suzuki pour rapprocher l’opérateur Time-Evolution _exp (-iHt)_ .

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a>Entrée

### <a name="trotterstepsize--double"></a>trotterStepSize : [double](xref:microsoft.quantum.lang-ref.double)

Durée de l’évolution de l’heure simulée dans une seule étape trotter.


### <a name="trotterorder--int"></a>trotterOrder : [entier](xref:microsoft.quantum.lang-ref.int)

Ordre de l’intégrateur trotter. Il doit s’agir de 1 ou d’un nombre pair.



## <a name="output--simulationalgorithm"></a>Sortie : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)

Type `SimulationAlgorithm`.