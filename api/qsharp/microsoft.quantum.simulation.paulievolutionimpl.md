---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Opération PauliEvolutionImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229135"
---
# <a name="paulievolutionimpl-operation"></a>Opération PauliEvolutionImpl

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de Pauli.

Pour plus d’informations, consultez [modélisation de générateurs dynamiques](/quantum/libraries/data-structures#dynamical-generator-modeling) .

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="generatorindex--generatorindex"></a>generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Index du générateur à représenter en tant qu’évolution unitaire dans la base Pauli.


### <a name="delta--double"></a>Delta : [double](xref:microsoft.quantum.lang-ref.double)

Multiplicateur sur la durée de l’évolution par rapport au terme référencé dans `generatorIndex` .


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Inscrivez-vous sur l’opérateur Time-Evolution.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

