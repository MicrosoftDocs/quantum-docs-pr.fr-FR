---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707721"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="8edf8-102">ObliviousAmplitudeAmplificationFromStatePreparation fonction)</span><span class="sxs-lookup"><span data-stu-id="8edf8-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="8edf8-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="8edf8-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="8edf8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8edf8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8edf8-105">Amplification d’amplitude oublie par Oracle pour les réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="8edf8-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="8edf8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="8edf8-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="8edf8-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="8edf8-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="8edf8-108">Phases de réflexions partielles</span><span class="sxs-lookup"><span data-stu-id="8edf8-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="8edf8-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="8edf8-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="8edf8-110">$A Oracle unitaire $ qui prépare l’état de démarrage auxiliaire</span><span class="sxs-lookup"><span data-stu-id="8edf8-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="8edf8-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="8edf8-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="8edf8-112">Oracle $O $ unitaire `ObliviousOracle` qui agit conjointement sur les registres auxiliaires et système</span><span class="sxs-lookup"><span data-stu-id="8edf8-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="8edf8-113">idxFlagQubit : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8edf8-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8edf8-114">Enregistrement d’un indicateur d’index qubit unique</span><span class="sxs-lookup"><span data-stu-id="8edf8-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="8edf8-115">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="8edf8-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8edf8-116">Opération qui implémente l’amplification d’amplitude oublie basée sur des réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="8edf8-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="8edf8-117">Notes</span><span class="sxs-lookup"><span data-stu-id="8edf8-117">Remarks</span></span>

<span data-ttu-id="8edf8-118">Cela impose des conditions plus strictes sur la forme des États de démarrage et cible auxiliaires que dans `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="8edf8-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="8edf8-119">Il est supposé que $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{Start}} \_ {FA} $ prépare l’état de démarrage auxiliaire $ \ket{\text{Start}} \_ {FA} $ à partir de la base de calcul $ \ket {0} \_ f\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="8edf8-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="8edf8-120">Il est supposé que l’État cible est marqué par $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="8edf8-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="8edf8-121">Il est supposé que \begin{align} O\ket {\ Text {Start}} \_ {FA} \ket{\Psi} \_ s = \lambda\ket {1} \_ f\ket {\ Text {tout}} \_ a\ket {\ Text {target}} \_ s U \ket{\Psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket f\cdots {0} \_ , \end{align} pour some Unity $U $.</span><span class="sxs-lookup"><span data-stu-id="8edf8-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>