---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Opération ContinuousPhaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703657"
---
# <a name="continuousphaseestimationiteration-operation"></a>Opération ContinuousPhaseEstimationIteration

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Packages [](https://nuget.org/packages/)


Exécute une seule itération d’un algorithme d’estimation de phase itérative (contrôlée de manière classique) à l’aide de puissances réelles arbitraires d’une entité Oracle.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
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

