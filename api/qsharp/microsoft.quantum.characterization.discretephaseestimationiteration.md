---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Opération DiscretePhaseEstimationIteration
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 8ce1e1a2bda6507285f055c87619a8760c891082
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204383"
---
# <a name="discretephaseestimationiteration-operation"></a>Opération DiscretePhaseEstimationIteration

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Exécute une seule itération d’un algorithme d’estimation de phase itérative (contrôlée de manière classique) à l’aide des puissances de nombre entier d’une entité Oracle.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="oracle--discreteoracle"></a>Oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Opération agissant sur un entier et un registre, de sorte que $U ^ m $ est appliqué au registre donné, où $U $ est l’unité de temps dont la phase doit être estimée, et où $m est la puissance de l’entier accordée à Oracle.


### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de fois où l’application Oracle unitaire donnée est appliquée.


### <a name="theta--double"></a>thêta : [double](xref:microsoft.quantum.lang-ref.double)

Angle d’inversion de la phase sur le contrôle qubit avant d’agir sur l’État cible.


### <a name="targetstate--qubit"></a>targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre d’état traité par l’entité Oracle donnée.


### <a name="controlqubit--qubit"></a>controlQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auxiliaire utilisé pour contrôler l’application du Oracle donné.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

