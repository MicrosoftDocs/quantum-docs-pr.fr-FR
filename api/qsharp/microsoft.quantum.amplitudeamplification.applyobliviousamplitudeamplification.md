---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Opération ApplyObliviousAmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707742"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="177d3-102">Opération ApplyObliviousAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="177d3-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="177d3-103">Espace de noms : [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="177d3-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="177d3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="177d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="177d3-105">Amplification d’amplitude oublie en spécifiant des réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="177d3-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="177d3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="177d3-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="177d3-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="177d3-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="177d3-108">Phases de réflexions partielles</span><span class="sxs-lookup"><span data-stu-id="177d3-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="177d3-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="177d3-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="177d3-110">Opérateur de réflexion à propos de l’état de démarrage du Registre auxiliaire</span><span class="sxs-lookup"><span data-stu-id="177d3-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="177d3-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="177d3-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="177d3-112">Opérateur de réflexion sur l’État cible du Registre auxiliaire</span><span class="sxs-lookup"><span data-stu-id="177d3-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="177d3-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="177d3-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="177d3-114">Oracle $O $ unitaire `ObliviousOracle` qui agit conjointement aux registres auxiliaires et système.</span><span class="sxs-lookup"><span data-stu-id="177d3-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="177d3-115">auxiliaryRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="177d3-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="177d3-116">Registre auxiliaire</span><span class="sxs-lookup"><span data-stu-id="177d3-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="177d3-117">systemRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="177d3-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="177d3-118">Registre système</span><span class="sxs-lookup"><span data-stu-id="177d3-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="177d3-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="177d3-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="177d3-120">Notes</span><span class="sxs-lookup"><span data-stu-id="177d3-120">Remarks</span></span>

<span data-ttu-id="177d3-121">Étant donné un état de démarrage auxiliaire particulier $ \ket{\text{Start}} \_ a $, un État cible auxiliaire particulier $ \ket{\text{Target}} \_ a $ et tout état système $ \ket{\Psi} \_ s $, supposons que \begin{align} O\ket {\ Text {Start}} \_ a\ket {\ PSI} \_ s = \lambda\ket{\text{Target}} \_ a U \ket{\Psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{Target} ^ \perp} \_ a\cdots \end{align} pour une unité $U $.</span><span class="sxs-lookup"><span data-stu-id="177d3-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="177d3-122">Par une séquence de réflexions sur les États de démarrage et de cible sur le registre auxiliaire entrelacé par les applications de `signalOracle` et ses voisins, la probabilité de réussite de l’application de U peut être modifiée.</span><span class="sxs-lookup"><span data-stu-id="177d3-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="177d3-123">Dans la plupart des cas, `auxiliaryRegister` est initialisé dans l’État $ \ket{\text{Start}} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="177d3-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="177d3-124">Références</span><span class="sxs-lookup"><span data-stu-id="177d3-124">References</span></span>

<span data-ttu-id="177d3-125">Consultez</span><span class="sxs-lookup"><span data-stu-id="177d3-125">See</span></span>

- <span data-ttu-id="177d3-126">[ *D.W. Berry, A.M. Childs, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) pour la version standard.</span><span class="sxs-lookup"><span data-stu-id="177d3-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="177d3-127">Consultez</span><span class="sxs-lookup"><span data-stu-id="177d3-127">See</span></span>
- <span data-ttu-id="177d3-128">[ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) pour une généralisation à des réflexions partielles.</span><span class="sxs-lookup"><span data-stu-id="177d3-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>