---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Opération RandomWalkPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845997"
---
# <a name="randomwalkphaseestimation-operation"></a>Opération RandomWalkPhaseEstimation

Espace de noms : [Microsoft. Quantum. Research. caractérisation](xref:Microsoft.Quantum.Research.Characterization)

Package : [Microsoft. Quantum. Research. caractérisation](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)


Effectue une estimation de phase itérative à l’aide d’un parcours aléatoire pour rapprocher l’inférence Bayésienne sur les résultats de mesure classiques d’un Oracle et d’un eigenstate donnés.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Entrée

### <a name="initialmean--double"></a>initialMean : [double](xref:microsoft.quantum.lang-ref.double)

Moyenne de la distribution antérieure normale initiale sur $ \Phi $.


### <a name="initialstddev--double"></a>initialStdDev : [double](xref:microsoft.quantum.lang-ref.double)

Écart type de la distribution initiale normale antérieure sur $ \Phi $.


### <a name="nmeasurements--int"></a>nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de mesures à accepter dans l’estimation POSTERIEURE finale.


### <a name="maxmeasurements--int"></a>maxMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre total de mesures que vous pouvez prendre avant que l’opération ne soit considérée comme ayant échoué.


### <a name="unwind--int"></a>déroulement : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de résultats à oublier lorsque les vérifications de cohérence échouent.


### <a name="oracle--continuousoracle"></a>Oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Opération représentant une unité de $U $ telle que $U (t) \ket{\Phi} = e ^ {i t \Phi}\ket{\Phi} $ pour eigenstates $ \ket{\Phi} $ avec la phase inconnue $ \Phi \Dans \mathbb{R} ^ + $.


### <a name="targetstate--qubit"></a>targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre sur lequel $U $ agit.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)

La dernière estimation $ \hat{\Phi} \mathrel{ : =} \expect [\Phi] $, où l’attente est sur le posterieure en raison de toutes les données acceptées.

## <a name="remarks"></a>Notes

### <a name="iterative-phase-estimation-and-eigenstates"></a>Estimation de phase itérative et Eigenstates

En général, le registre d’entrée `eigenstate` n’a pas besoin d’être un eigenstate $ \ket{\Phi} $ de $U $, mais il peut s’agir d’une superposition sur eigenstates. Supposons que l’état d’entrée soit donné par \begin{align} \ket{\Psi} & = \sum \_ {j} \alpha \_ j \ket{\Phi \_ j}, \end{align} où $ \{ \alpha \_ j \} $ est un coefficient complexe, de sorte que $ \sum \_ j | \alpha \_ j | ^ 2 = $1 et où $U \ket{\Phi \_ j} = \Phi \_ j\ket {\ Phi \_ j} $.

Ensuite, l’estimation de la phase itérative finit par converger vers un eigenstate unique, comme décrit dans le [Guide de développement](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).

### <a name="experiment-design"></a>Conception d’expérimentation

Les temps de mesure $t $ et les angles d’inversion $ \Theta $ passés à `oracle` sont choisis en fonction de l' *heuristique* de l’estimation de la particule, \Begin{align} \Theta \sim \Pr (\Phi), \quad t \approx \frac {1} {\variance{\Phi}}.
\end{align} cette heuristique est optimale pour réduire la variance POSTERIEURE attendue dans l’estimation de la phase itérative en supposant une normale avant.

### <a name="optimality"></a>Optimalité

Cette opération se rapproche de l’estimateur optimal pour la phase $ \Phi $, évaluée à l’aide de la perte quadratique $L (\Phi, \hat{\Phi}) \mathrel{ : =} (\Phi-\hat{\Phi}) ^ 2 $.

Pour plus d’informations sur les statistiques de l’estimation de la phase itérative, consultez estimation de la [phase bayésienne](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .

## <a name="references"></a>Références

- Ferris *et al.* 2011 [doi : 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv : 1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [doi : 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv : 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe et Granade 2018 *(en préparation)*.