---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: Opération AdiabaticStateEnergyUnitary
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: a69eb29318a750bea9c7c84ae4f90f7a31007c33
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225531"
---
# <a name="adiabaticstateenergyunitary-operation"></a>Opération AdiabaticStateEnergyUnitary

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Exécute la préparation de l’État en appliquant un `statePrepUnitary` à l’état d’entrée, suivi de la préparation de l’état de adiabatic à l’aide d’un et d’une `adiabaticUnitary` estimation de la phase finale en ce qui concerne `qpeUnitary` l’état résultant à l’aide d’un `phaseEstAlgorithm` .

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a>Entrée

### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Oracle qui représente la préparation de l’état du générateur dynamique initial.


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Oracle représentant l’algorithme d’évolution adiabatic à utiliser pour implémenter les balayages à l’état final de l’algorithme.


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a>qpeUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Oracle représentant un opérateur d’unités $U $ représentant l’évolution de l’heure $ \delta t $ sous un générateur dynamique avec l’état du sol $ \ket{\Phi} $ et l’énergie de l’état du sol $E = \Phi \\ , \delta t $.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [double](xref:microsoft.quantum.lang-ref.double) 

Opération qui effectue une estimation de phase sur une opération unitaire donnée.
Pour plus d’informations, consultez estimation de la [phase itérative](/quantum/libraries/characterization#iterative-phase-estimation) .


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre de qubits à utiliser pour effectuer la simulation.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

Estimation $ \hat{\Phi} $ de l’énergie de l’état du sol $ \Phi $ du générateur représenté par $U $.