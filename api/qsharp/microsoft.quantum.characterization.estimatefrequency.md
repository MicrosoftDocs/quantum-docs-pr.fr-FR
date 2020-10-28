---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Opération EstimateFrequency
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703660"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="ebe03-102">Opération EstimateFrequency</span><span class="sxs-lookup"><span data-stu-id="ebe03-102">EstimateFrequency operation</span></span>

<span data-ttu-id="ebe03-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="ebe03-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="ebe03-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ebe03-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ebe03-105">À partir d’une préparation et d’une mesure, évalue la fréquence à laquelle cette mesure s’est déroulée (retourne `Zero` ) en effectuant un nombre donné d’essais.</span><span class="sxs-lookup"><span data-stu-id="ebe03-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="ebe03-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ebe03-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="ebe03-107">préparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebe03-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ebe03-108">Une opération $P $ qui prépare un État donné $ \rho $ sur son registre d’entrée.</span><span class="sxs-lookup"><span data-stu-id="ebe03-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="ebe03-109">mesure : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="ebe03-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="ebe03-110">Une opération $M $ représentant la mesure de l’intérêt.</span><span class="sxs-lookup"><span data-stu-id="ebe03-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="ebe03-111">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebe03-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebe03-112">Nombre de qubits sur lesquelles la préparation et la mesure se font.</span><span class="sxs-lookup"><span data-stu-id="ebe03-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="ebe03-113">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebe03-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebe03-114">Nombre de fois où la mesure doit être exécutée afin d’estimer la fréquence d’intérêt.</span><span class="sxs-lookup"><span data-stu-id="ebe03-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="ebe03-115">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ebe03-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ebe03-116">Estimation de $ \hat{p} $ de la fréquence avec laquelle $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ retourne `Zero` , obtenue à l’aide de l’estimateur binomiale non biaisé $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, où $n \_ {\uparrow} $ est le nombre de `Zero` résultats observés.</span><span class="sxs-lookup"><span data-stu-id="ebe03-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="ebe03-117">Cela est particulièrement important sur les ordinateurs cibles qui respectent les limitations physiques, de sorte que les probabilités ne peuvent pas être mesurées.</span><span class="sxs-lookup"><span data-stu-id="ebe03-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>