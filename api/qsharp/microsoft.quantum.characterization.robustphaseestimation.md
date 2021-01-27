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
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="501e3-102">Opération RobustPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="501e3-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="501e3-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="501e3-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="501e3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="501e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="501e3-105">Exécute l’algorithme d’estimation de phase quantique non itérative fiable pour un serveur Oracle `U` et eigenstate donné, et fournit une estimation réelle de la phase avec la mise à l’échelle des écarts à la limite Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="501e3-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="501e3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="501e3-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="501e3-107">bitsPrecision : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="501e3-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="501e3-108">Cela fournit une estimation de $ \Phi $ avec l’écart type $ \sigma \Le 2 \ pi/2 ^ \text{bitsPrecision} $ à l’aide de plusieurs requêtes de mise à l’échelle, telles que $ \sigma \Le 10,7 \pi/\text{# de requêtes} $.</span><span class="sxs-lookup"><span data-stu-id="501e3-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="501e3-109">Oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="501e3-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="501e3-110">Une opération qui implémente $U ^ m $ pour des valeurs entières données $m $.</span><span class="sxs-lookup"><span data-stu-id="501e3-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="501e3-111">targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="501e3-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="501e3-112">Registre quantique sur lequel $U $ agit.</span><span class="sxs-lookup"><span data-stu-id="501e3-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="501e3-113">S’il stocke un eigenstate $ \ket{\Phi} $ de $U $, $U \ket{\Phi} = e ^ {i\phi} \ket{\Phi} $ pour $ \phi\in (-\pi, \pi] $ une phase inconnue.</span><span class="sxs-lookup"><span data-stu-id="501e3-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="501e3-114">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="501e3-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="501e3-115">Notes</span><span class="sxs-lookup"><span data-stu-id="501e3-115">Remarks</span></span>

<span data-ttu-id="501e3-116">Dans la limite d’un grand nombre de requêtes, Cramer-Rao limites inférieures pour l’écart type de l’estimation de $ \Phi $ satisfont à $ \sigma \ge 2 \pi/\text{# de requêtes} $.</span><span class="sxs-lookup"><span data-stu-id="501e3-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="501e3-117">Références</span><span class="sxs-lookup"><span data-stu-id="501e3-117">References</span></span>

- <span data-ttu-id="501e3-118">Étalonnage robuste d’un Single-Qubit universel Gate-Set à l’aide d’une estimation de phase robuste Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="501e3-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>