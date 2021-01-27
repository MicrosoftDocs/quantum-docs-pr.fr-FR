---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: Opération EstimateOverlapBetweenStates
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: e083d6da13b0780905bf365c7a428ebc9666ce9e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839713"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="b5343-102">Opération EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="b5343-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="b5343-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="b5343-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="b5343-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5343-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5343-105">À partir de deux opérations qui préparent les copies d’un État, évalue le chevauchement carré entre les États préparés par chaque opération.</span><span class="sxs-lookup"><span data-stu-id="b5343-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="b5343-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b5343-106">Input</span></span>

### <a name="preparation1--qubit--unit--is-adj"></a><span data-ttu-id="b5343-107">preparation1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="b5343-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b5343-108">La première des deux opérations de préparation de l’État à comparer.</span><span class="sxs-lookup"><span data-stu-id="b5343-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj"></a><span data-ttu-id="b5343-109">preparation2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="b5343-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b5343-110">Deuxième des deux opérations de préparation de l’État à comparer.</span><span class="sxs-lookup"><span data-stu-id="b5343-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="b5343-111">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5343-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5343-112">Nombre de qubits sur lesquels `commonPreparation` , `preparation1` et `preparation2` agissent.</span><span class="sxs-lookup"><span data-stu-id="b5343-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="b5343-113">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5343-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5343-114">Nombre de mesures à utiliser pour estimer le chevauchement.</span><span class="sxs-lookup"><span data-stu-id="b5343-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="b5343-115">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5343-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="b5343-116">Notes</span><span class="sxs-lookup"><span data-stu-id="b5343-116">Remarks</span></span>

<span data-ttu-id="b5343-117">Cette opération utilise le test d’échange pour trouver $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $ où $U $ est la représentation unitaire de l’action de `preparation1` , et où $V $ correspond à `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="b5343-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5343-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5343-118">See Also</span></span>

- [<span data-ttu-id="b5343-119">Microsoft. Quantum. caractérisation. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="b5343-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="b5343-120">Microsoft. Quantum. caractérisation. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="b5343-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)