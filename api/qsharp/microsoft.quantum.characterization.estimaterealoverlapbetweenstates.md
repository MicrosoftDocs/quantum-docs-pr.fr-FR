---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: Opération EstimateRealOverlapBetweenStates
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703612"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="d3fe5-102">Opération EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="d3fe5-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="d3fe5-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d3fe5-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d3fe5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3fe5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3fe5-105">À partir de deux opérations qui préparent les copies d’un État, évalue la partie réelle du chevauchement entre les États préparés par chaque opération.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="d3fe5-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d3fe5-106">Input</span></span>

### <a name="commonpreparation--qubit--unit-adj"></a><span data-ttu-id="d3fe5-107">commonPreparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3fe5-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d3fe5-108">Opération qui prépare un état d’entrée fixe.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit-adj--ctl"></a><span data-ttu-id="d3fe5-109">preparation1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="d3fe5-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d3fe5-110">La première des deux opérations de préparation de l’État à comparer.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj--ctl"></a><span data-ttu-id="d3fe5-111">preparation2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="d3fe5-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d3fe5-112">Deuxième des deux opérations de préparation de l’État à comparer.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="d3fe5-113">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3fe5-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3fe5-114">Nombre de qubits sur lesquels `commonPreparation` , `preparation1` et `preparation2` agissent.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d3fe5-115">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3fe5-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3fe5-116">Nombre de mesures à utiliser pour estimer le chevauchement.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="d3fe5-117">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3fe5-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="d3fe5-118">Notes</span><span class="sxs-lookup"><span data-stu-id="d3fe5-118">Remarks</span></span>

<span data-ttu-id="d3fe5-119">Cette opération utilise le test Hadarmard pour rechercher la partie réelle de $ $ \begin{align} \braket{\Psi | V ^ {\dagger} U | \Psi} \end{align} $ $ où $ \ket{\Psi} $ est l’état préparé par `commonPreparation` , $U $ est la représentation unitaire de l’action de `preparation1` , et où $V $ correspond à `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="d3fe5-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="d3fe5-120">Références</span><span class="sxs-lookup"><span data-stu-id="d3fe5-120">References</span></span>

- <span data-ttu-id="d3fe5-121">Aharonov *et al.* [quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3fe5-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3fe5-122">See Also</span></span>

- [<span data-ttu-id="d3fe5-123">Microsoft. Quantum. caractérisation. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="d3fe5-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="d3fe5-124">Microsoft. Quantum. caractérisation. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="d3fe5-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)