---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Opération EstimateEnergy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: ba4a5372aaf092c3ac3a1302f9715ca643be8436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707817"
---
# <a name="estimateenergy-operation"></a>Opération EstimateEnergy

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Exécute la préparation de l’État en appliquant un `statePrepUnitary` sur une estimation de phase d’état d’entrée allouée automatiquement par rapport à `qpeUnitary` l’état résultant à l’aide d’un `phaseEstAlgorithm` .

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits utilisés pour effectuer la simulation.


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Oracle qui représente la préparation de l’état du générateur dynamique initial.


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

Oracle représentant un opérateur d’unités $U $ représentant l’évolution de l’heure $ \delta t $ sous un générateur dynamique avec l’état du sol $ \ket{\Phi} $ et l’énergie de l’état du sol $E = \Phi \\ , \delta t $.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [double](xref:microsoft.quantum.lang-ref.double) 

Opération qui effectue une estimation de phase sur une opération unitaire donnée.
Pour plus d’informations, consultez estimation de la [phase itérative](/quantum/libraries/characterization#iterative-phase-estimation) .



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Estimation $ \hat{\Phi} $ de l’énergie de l’état du sol $ \Phi $ de l’énergie de l’état du sol du générateur représenté par $U $.