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
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="55f30-102">Opération ContinuousPhaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="55f30-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="55f30-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="55f30-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="55f30-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55f30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55f30-105">Exécute une seule itération d’un algorithme d’estimation de phase itérative (contrôlée de manière classique) à l’aide de puissances réelles arbitraires d’une entité Oracle.</span><span class="sxs-lookup"><span data-stu-id="55f30-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="55f30-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="55f30-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="55f30-107">Oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="55f30-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="55f30-108">L’opération agissant sur un double $t $ et un registre, de sorte que $U ^ t $ est appliqué au registre donné, où $U $ correspond à l’unité de temps dont la phase doit être estimée, et où $t $ est la puissance de l’entier accordée à Oracle.</span><span class="sxs-lookup"><span data-stu-id="55f30-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="55f30-109">heure : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="55f30-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="55f30-110">Nombre de fois où l’application Oracle unitaire donnée est appliquée.</span><span class="sxs-lookup"><span data-stu-id="55f30-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="55f30-111">thêta : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="55f30-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="55f30-112">Angle d’inversion de la phase sur le contrôle qubit avant d’agir sur l’État cible.</span><span class="sxs-lookup"><span data-stu-id="55f30-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="55f30-113">targetState : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="55f30-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="55f30-114">Registre d’état traité par l’entité Oracle donnée.</span><span class="sxs-lookup"><span data-stu-id="55f30-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="55f30-115">controlQubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="55f30-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="55f30-116">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55f30-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

