---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Opération EstimateFrequencyA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 6cca8dff70283e0d69441db8a5b31fb5bfb3082a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839927"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="7c1a3-102">Opération EstimateFrequencyA</span><span class="sxs-lookup"><span data-stu-id="7c1a3-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="7c1a3-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="7c1a3-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="7c1a3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c1a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c1a3-105">Étant donné une préparation qui est adjointable et mesure, évalue la fréquence à laquelle cette mesure s’est déroulée (retourne `Zero` ) en effectuant un nombre donné d’essais.</span><span class="sxs-lookup"><span data-stu-id="7c1a3-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="7c1a3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7c1a3-106">Input</span></span>

### <a name="preparation--qubit--unit--is-adj"></a><span data-ttu-id="7c1a3-107">préparation : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="7c1a3-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7c1a3-108">Une opération adjointable $P $ qui prépare un État donné $ \rho $ dans son registre d’entrée.</span><span class="sxs-lookup"><span data-stu-id="7c1a3-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="7c1a3-109">mesure : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="7c1a3-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="7c1a3-110">Une opération $M $ représentant la mesure de l’intérêt.</span><span class="sxs-lookup"><span data-stu-id="7c1a3-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="7c1a3-111">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7c1a3-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7c1a3-112">Nombre de qubits sur lesquelles la préparation et la mesure se font.</span><span class="sxs-lookup"><span data-stu-id="7c1a3-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="7c1a3-113">nMeasurements : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7c1a3-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7c1a3-114">Nombre de fois où la mesure doit être exécutée afin d’estimer la fréquence d’intérêt.</span><span class="sxs-lookup"><span data-stu-id="7c1a3-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="7c1a3-115">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c1a3-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c1a3-116">Estimation de $ \hat{p} $ de la fréquence avec laquelle $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ retourne `Zero` , obtenue à l’aide de l’estimateur binomiale non biaisé $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, où $n \_ {\uparrow} $ est le nombre de `Zero` résultats observés.</span><span class="sxs-lookup"><span data-stu-id="7c1a3-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c1a3-117">Notes</span><span class="sxs-lookup"><span data-stu-id="7c1a3-117">Remarks</span></span>

<span data-ttu-id="7c1a3-118">Pour les opérations adjointable, certaines hypothèses peuvent être apportées telles que l’appel de l’opération prépare le qubits à exactement le même État, ce qui permet aux ordinateurs cibles d’effectuer des optimisations de performances.</span><span class="sxs-lookup"><span data-stu-id="7c1a3-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>