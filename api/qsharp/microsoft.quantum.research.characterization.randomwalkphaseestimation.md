---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Opération RandomWalkPhaseEstimation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 2c3afdd41da24a1f32f59f36f0f5c5ed29df1f0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226160"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="df120-102">Opération RandomWalkPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="df120-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="df120-103">Espace de noms : [Microsoft. Quantum. Research. caractérisation](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="df120-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="df120-104">Package : [Microsoft. Quantum. Research. caractérisation](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="df120-104">Package: [Microsoft.Quantum.Research.Characterization](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span></span>


<span data-ttu-id="df120-105">Effectue une estimation de phase itérative à l’aide d’un parcours aléatoire pour rapprocher l’inférence Bayésienne sur les résultats de mesure classiques d’un Oracle et d’un eigenstate donnés.</span><span class="sxs-lookup"><span data-stu-id="df120-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="df120-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="df120-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="df120-107">initialMean : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df120-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df120-108">Moyenne de la distribution antérieure normale initiale sur $ \Phi $.</span><span class="sxs-lookup"><span data-stu-id="df120-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="df120-109">initialStdDev : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df120-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df120-110">Écart type de la distribution initiale normale antérieure sur $ \Phi $.</span><span class="sxs-lookup"><span data-stu-id="df120-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="df120-111">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df120-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df120-112">Nombre de mesures à accepter dans l’estimation POSTERIEURE finale.</span><span class="sxs-lookup"><span data-stu-id="df120-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="df120-113">maxMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df120-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df120-114">Nombre total de mesures que vous pouvez prendre avant que l’opération ne soit considérée comme ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="df120-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="df120-115">déroulement : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df120-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df120-116">Nombre de résultats à oublier lorsque les vérifications de cohérence échouent.</span><span class="sxs-lookup"><span data-stu-id="df120-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="df120-117">Oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="df120-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="df120-118">Opération représentant une unité de $U $ telle que $U (t) \ket{\Phi} = e ^ {i t \Phi}\ket{\Phi} $ pour eigenstates $ \ket{\Phi} $ avec la phase inconnue $ \Phi \Dans \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="df120-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="df120-119">targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="df120-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="df120-120">Registre sur lequel $U $ agit.</span><span class="sxs-lookup"><span data-stu-id="df120-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="df120-121">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df120-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df120-122">La dernière estimation $ \hat{\Phi} \mathrel{ : =} \expect [\Phi] $, où l’attente est sur le posterieure en raison de toutes les données acceptées.</span><span class="sxs-lookup"><span data-stu-id="df120-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="df120-123">Notes</span><span class="sxs-lookup"><span data-stu-id="df120-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="df120-124">Estimation de phase itérative et Eigenstates</span><span class="sxs-lookup"><span data-stu-id="df120-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="df120-125">En général, le registre d’entrée `eigenstate` n’a pas besoin d’être un eigenstate $ \ket{\Phi} $ de $U $, mais il peut s’agir d’une superposition sur eigenstates.</span><span class="sxs-lookup"><span data-stu-id="df120-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="df120-126">Supposons que l’état d’entrée soit donné par \begin{align} \ket{\Psi} & = \sum \_ {j} \alpha \_ j \ket{\Phi \_ j}, \end{align} où $ \{ \alpha \_ j \} $ est un coefficient complexe, de sorte que $ \sum \_ j | \alpha \_ j | ^ 2 = $1 et où $U \ket{\Phi \_ j} = \Phi \_ j\ket {\ Phi \_ j} $.</span><span class="sxs-lookup"><span data-stu-id="df120-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="df120-127">Ensuite, l’estimation de la phase itérative finit par converger vers un eigenstate unique, comme décrit dans le [Guide de développement](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span><span class="sxs-lookup"><span data-stu-id="df120-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="df120-128">Conception d’expérimentation</span><span class="sxs-lookup"><span data-stu-id="df120-128">Experiment Design</span></span>

<span data-ttu-id="df120-129">Les temps de mesure $t $ et les angles d’inversion $ \Theta $ passés à `oracle` sont choisis en fonction de l' *heuristique* de l’estimation de la particule, \Begin{align} \Theta \sim \Pr (\Phi), \quad t \approx \frac {1} {\variance{\Phi}}.</span><span class="sxs-lookup"><span data-stu-id="df120-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic*, \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="df120-130">\end{align} cette heuristique est optimale pour réduire la variance POSTERIEURE attendue dans l’estimation de la phase itérative en supposant une normale avant.</span><span class="sxs-lookup"><span data-stu-id="df120-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="df120-131">Optimalité</span><span class="sxs-lookup"><span data-stu-id="df120-131">Optimality</span></span>

<span data-ttu-id="df120-132">Cette opération se rapproche de l’estimateur optimal pour la phase $ \Phi $, évaluée à l’aide de la perte quadratique $L (\Phi, \hat{\Phi}) \mathrel{ : =} (\Phi-\hat{\Phi}) ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="df120-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="df120-133">Pour plus d’informations sur les statistiques de l’estimation de la phase itérative, consultez estimation de la [phase bayésienne](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="df120-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="df120-134">Références</span><span class="sxs-lookup"><span data-stu-id="df120-134">References</span></span>

- <span data-ttu-id="df120-135">Ferris *et al.* 2011 [doi : 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv : 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="df120-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="df120-136">Wiebe *et al.* 2013 [doi : 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv : 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="df120-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="df120-137">Wiebe et Granade 2018 *(en préparation)*.</span><span class="sxs-lookup"><span data-stu-id="df120-137">Wiebe and Granade 2018 *(in preparation)*.</span></span>