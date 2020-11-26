---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: Opération EstimateRealOverlapBetweenStates
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: d9f569ceffc16f377189dc94035213b9075609cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216181"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="1ad18-102">Opération EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="1ad18-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="1ad18-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1ad18-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1ad18-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ad18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ad18-105">À partir de deux opérations qui préparent les copies d’un État, évalue la partie réelle du chevauchement entre les États préparés par chaque opération.</span><span class="sxs-lookup"><span data-stu-id="1ad18-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="1ad18-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1ad18-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="1ad18-107">commonPreparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="1ad18-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1ad18-108">Opération qui prépare un état d’entrée fixe.</span><span class="sxs-lookup"><span data-stu-id="1ad18-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="1ad18-109">preparation1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1ad18-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1ad18-110">La première des deux opérations de préparation de l’État à comparer.</span><span class="sxs-lookup"><span data-stu-id="1ad18-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="1ad18-111">preparation2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1ad18-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1ad18-112">Deuxième des deux opérations de préparation de l’État à comparer.</span><span class="sxs-lookup"><span data-stu-id="1ad18-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="1ad18-113">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1ad18-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1ad18-114">Nombre de qubits sur lesquels `commonPreparation` , `preparation1` et `preparation2` agissent.</span><span class="sxs-lookup"><span data-stu-id="1ad18-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="1ad18-115">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1ad18-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1ad18-116">Nombre de mesures à utiliser pour estimer le chevauchement.</span><span class="sxs-lookup"><span data-stu-id="1ad18-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="1ad18-117">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1ad18-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="1ad18-118">Notes</span><span class="sxs-lookup"><span data-stu-id="1ad18-118">Remarks</span></span>

<span data-ttu-id="1ad18-119">Cette opération utilise le test Hadarmard pour rechercher la partie réelle de $ $ \begin{align} \braket{\Psi | V ^ {\dagger} U | \Psi} \end{align} $ $ où $ \ket{\Psi} $ est l’état préparé par `commonPreparation` , $U $ est la représentation unitaire de l’action de `preparation1` , et où $V $ correspond à `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="1ad18-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="1ad18-120">Références</span><span class="sxs-lookup"><span data-stu-id="1ad18-120">References</span></span>

- <span data-ttu-id="1ad18-121">Aharonov *et al.* [quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="1ad18-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ad18-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ad18-122">See Also</span></span>

- [<span data-ttu-id="1ad18-123">Microsoft. Quantum. caractérisation. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="1ad18-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="1ad18-124">Microsoft. Quantum. caractérisation. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="1ad18-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)