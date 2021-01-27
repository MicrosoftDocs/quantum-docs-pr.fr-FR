---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Opération ContinuousPhaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851910"
---
# <a name="continuousphaseestimationiteration-operation"></a>Opération ContinuousPhaseEstimationIteration

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Exécute une seule itération d’un algorithme d’estimation de phase itérative (contrôlée de manière classique) à l’aide de puissances réelles arbitraires d’une entité Oracle.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="oracle--continuousoracle"></a>Oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

L’opération agissant sur un double $t $ et un registre, de sorte que $U ^ t $ est appliqué au registre donné, où $U $ correspond à l’unité de temps dont la phase doit être estimée, et où $t $ est la puissance de l’entier accordée à Oracle.


### <a name="time--double"></a>heure : [double](xref:microsoft.quantum.lang-ref.double)

Nombre de fois où l’application Oracle unitaire donnée est appliquée.


### <a name="theta--double"></a>thêta : [double](xref:microsoft.quantum.lang-ref.double)

Angle d’inversion de la phase sur le contrôle qubit avant d’agir sur l’État cible.


### <a name="targetstate--qubit"></a>targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre d’état traité par l’entité Oracle donnée.


### <a name="controlqubit--qubit"></a>controlQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

