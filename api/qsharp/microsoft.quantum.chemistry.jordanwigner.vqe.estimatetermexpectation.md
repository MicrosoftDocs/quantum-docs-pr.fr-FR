---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Opération EstimateTermExpectation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703078"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="93d8e-102">Opération EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="93d8e-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="93d8e-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="93d8e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="93d8e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93d8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93d8e-105">Calcule l’énergie associée à un terme Jordan-Wigner Hamilton</span><span class="sxs-lookup"><span data-stu-id="93d8e-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="93d8e-106">Description</span><span class="sxs-lookup"><span data-stu-id="93d8e-106">Description</span></span>

<span data-ttu-id="93d8e-107">Cette opération estime la valeur de prévision associée à chaque opérateur de mesure et la multiplie par le coefficient correspondant, à l’aide de l’échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="93d8e-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="93d8e-108">Les résultats sont regroupés dans une variable contenant l’énergie du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="93d8e-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="93d8e-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="93d8e-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="93d8e-110">inputStateUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93d8e-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="93d8e-111">Unité utilisée pour la préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="93d8e-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="93d8e-112">OPS : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="93d8e-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="93d8e-113">Les opérateurs de mesure du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="93d8e-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="93d8e-114">coeffs : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="93d8e-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="93d8e-115">Coefficients du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="93d8e-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="93d8e-116">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="93d8e-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="93d8e-117">Nombre de qubits nécessaires pour simuler le système moléculaire.</span><span class="sxs-lookup"><span data-stu-id="93d8e-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="93d8e-118">nSamples : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="93d8e-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="93d8e-119">Nombre d’échantillons à utiliser pour l’estimation du terme attendu.</span><span class="sxs-lookup"><span data-stu-id="93d8e-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="93d8e-120">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="93d8e-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="93d8e-121">Énergie associée au terme de Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="93d8e-121">The energy associated to the Jordan-Wigner term.</span></span>