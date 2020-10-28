---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Opération QuantumPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703600"
---
# <a name="quantumphaseestimation-operation"></a>Opération QuantumPhaseEstimation

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Packages [](https://nuget.org/packages/)


Exécute l’algorithme d’estimation de phase quantique pour un Oracle donné `U` et `targetState` , en lisant la phase dans un registre quantique Big-endian.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Entrée

### <a name="oracle--discreteoracle"></a>Oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Une opération qui implémente $U ^ m $ pour les nombres entiers fournis est de m.


### <a name="targetstate--qubit"></a>targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre quantique représentant l’État $ \ket{\Phi} $ traité par $U $. Si $ \ket{\Phi} $ est un eigenstate de $U $, $U \ket{\Phi} = e ^ {i\phi} \ket{\Phi} $ pour $ \Phi \Dans [0, 2 \ pi) $ une phase inconnue.


### <a name="controlregister--bigendian"></a>controlRegister : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registre d’entiers de représentation Big endian qui peut être utilisé pour contrôler le Oracle fourni, et qui contient la représentation de $ \Phi $ à la suite de l’application de cette opération. Le controlRegister est supposé démarrer à l’état initial $ \ket{00\cdots 0} $, où la longueur du registre indique la précision souhaitée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

