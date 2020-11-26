---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: Opération JordanWignerFermionImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: e0e0afe0f0998acb9791ceb25975fe8005771ed0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224936"
---
# <a name="jordanwignerfermionimpl-operation"></a>Opération JordanWignerFermionImpl

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de JordanWigner.

Pour plus d’informations, consultez [modélisation de générateurs dynamiques](../libraries/data-structures#dynamical-generator-modeling) .

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="generatorindex--generatorindex"></a>generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Index de générateur à représenter comme évolution unitaire dans le JordanWigner.


### <a name="stepsize--double"></a>Procédure : [double](xref:microsoft.quantum.lang-ref.double)

Multiplicateur sur la durée de l’évolution par rapport au terme référencé dans `generatorIndex` .


### <a name="qubits--qubit"></a>qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Inscrivez-vous sur l’opérateur Time-Evolution.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

