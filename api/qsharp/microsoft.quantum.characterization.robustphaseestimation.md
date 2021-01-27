---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Opération RobustPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851799"
---
# <a name="robustphaseestimation-operation"></a>Opération RobustPhaseEstimation

Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Exécute l’algorithme d’estimation de phase quantique non itérative fiable pour un serveur Oracle `U` et eigenstate donné, et fournit une estimation réelle de la phase avec la mise à l’échelle des écarts à la limite Heisenberg.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Entrée

### <a name="bitsprecision--int"></a>bitsPrecision : [entier](xref:microsoft.quantum.lang-ref.int)

Cela fournit une estimation de $ \Phi $ avec l’écart type $ \sigma \Le 2 \ pi/2 ^ \text{bitsPrecision} $ à l’aide de plusieurs requêtes de mise à l’échelle, telles que $ \sigma \Le 10,7 \pi/\text{# de requêtes} $.


### <a name="oracle--discreteoracle"></a>Oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Une opération qui implémente $U ^ m $ pour des valeurs entières données $m $.


### <a name="targetstate--qubit"></a>targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre quantique sur lequel $U $ agit. S’il stocke un eigenstate $ \ket{\Phi} $ de $U $, $U \ket{\Phi} = e ^ {i\phi} \ket{\Phi} $ pour $ \phi\in (-\pi, \pi] $ une phase inconnue.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Notes

Dans la limite d’un grand nombre de requêtes, Cramer-Rao limites inférieures pour l’écart type de l’estimation de $ \Phi $ satisfont à $ \sigma \ge 2 \pi/\text{# de requêtes} $.

## <a name="references"></a>Références

- Étalonnage robuste d’un Single-Qubit universel Gate-Set à l’aide d’une estimation de phase robuste Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677