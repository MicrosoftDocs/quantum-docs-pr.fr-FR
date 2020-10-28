---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Opération EstimateEnergy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: ba4a5372aaf092c3ac3a1302f9715ca643be8436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707817"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="9241b-102">Opération EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="9241b-102">EstimateEnergy operation</span></span>

<span data-ttu-id="9241b-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9241b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9241b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9241b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9241b-105">Exécute la préparation de l’État en appliquant un `statePrepUnitary` sur une estimation de phase d’état d’entrée allouée automatiquement par rapport à `qpeUnitary` l’état résultant à l’aide d’un `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="9241b-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="9241b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9241b-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="9241b-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9241b-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9241b-108">Nombre de qubits utilisés pour effectuer la simulation.</span><span class="sxs-lookup"><span data-stu-id="9241b-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="9241b-109">statePrepUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9241b-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9241b-110">Oracle qui représente la préparation de l’état du générateur dynamique initial.</span><span class="sxs-lookup"><span data-stu-id="9241b-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="9241b-111">qpeUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="9241b-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9241b-112">Oracle représentant un opérateur d’unités $U $ représentant l’évolution de l’heure $ \delta t $ sous un générateur dynamique avec l’état du sol $ \ket{\Phi} $ et l’énergie de l’état du sol $E = \Phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="9241b-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="9241b-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9241b-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="9241b-114">Opération qui effectue une estimation de phase sur une opération unitaire donnée.</span><span class="sxs-lookup"><span data-stu-id="9241b-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="9241b-115">Pour plus d’informations, consultez estimation de la [phase itérative](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="9241b-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="9241b-116">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9241b-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9241b-117">Estimation $ \hat{\Phi} $ de l’énergie de l’état du sol $ \Phi $ de l’énergie de l’état du sol du générateur représenté par $U $.</span><span class="sxs-lookup"><span data-stu-id="9241b-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>