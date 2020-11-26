---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: Opération AdiabaticStateEnergyUnitary
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: a69eb29318a750bea9c7c84ae4f90f7a31007c33
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225531"
---
# <a name="adiabaticstateenergyunitary-operation"></a><span data-ttu-id="24f02-102">Opération AdiabaticStateEnergyUnitary</span><span class="sxs-lookup"><span data-stu-id="24f02-102">AdiabaticStateEnergyUnitary operation</span></span>

<span data-ttu-id="24f02-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="24f02-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="24f02-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24f02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24f02-105">Exécute la préparation de l’État en appliquant un `statePrepUnitary` à l’état d’entrée, suivi de la préparation de l’état de adiabatic à l’aide d’un et d’une `adiabaticUnitary` estimation de la phase finale en ce qui concerne `qpeUnitary` l’état résultant à l’aide d’un `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="24f02-105">Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="24f02-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="24f02-106">Input</span></span>

### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="24f02-107">statePrepUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24f02-107">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="24f02-108">Oracle qui représente la préparation de l’état du générateur dynamique initial.</span><span class="sxs-lookup"><span data-stu-id="24f02-108">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="24f02-109">adiabaticUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24f02-109">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="24f02-110">Oracle représentant l’algorithme d’évolution adiabatic à utiliser pour implémenter les balayages à l’état final de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="24f02-110">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="24f02-111">qpeUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="24f02-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="24f02-112">Oracle représentant un opérateur d’unités $U $ représentant l’évolution de l’heure $ \delta t $ sous un générateur dynamique avec l’état du sol $ \ket{\Phi} $ et l’énergie de l’état du sol $E = \Phi \\ , \delta t $.</span><span class="sxs-lookup"><span data-stu-id="24f02-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="24f02-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="24f02-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="24f02-114">Opération qui effectue une estimation de phase sur une opération unitaire donnée.</span><span class="sxs-lookup"><span data-stu-id="24f02-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="24f02-115">Pour plus d’informations, consultez estimation de la [phase itérative](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="24f02-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="24f02-116">qubits : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="24f02-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="24f02-117">Un registre de qubits à utiliser pour effectuer la simulation.</span><span class="sxs-lookup"><span data-stu-id="24f02-117">A register of qubits to be used to perform the simulation.</span></span>



## <a name="output--double"></a><span data-ttu-id="24f02-118">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="24f02-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="24f02-119">Estimation $ \hat{\Phi} $ de l’énergie de l’état du sol $ \Phi $ du générateur représenté par $U $.</span><span class="sxs-lookup"><span data-stu-id="24f02-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>