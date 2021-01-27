---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Opération EstimateTermExpectation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835667"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="37479-102">Opération EstimateTermExpectation</span><span class="sxs-lookup"><span data-stu-id="37479-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="37479-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="37479-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="37479-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="37479-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="37479-105">Calcule l’énergie associée à un terme Jordan-Wigner Hamilton</span><span class="sxs-lookup"><span data-stu-id="37479-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="37479-106">Description</span><span class="sxs-lookup"><span data-stu-id="37479-106">Description</span></span>

<span data-ttu-id="37479-107">Cette opération estime la valeur de prévision associée à chaque opérateur de mesure et la multiplie par le coefficient correspondant, à l’aide de l’échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="37479-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="37479-108">Les résultats sont regroupés dans une variable contenant l’énergie du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="37479-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="37479-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="37479-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="37479-110">inputStateUnitary : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="37479-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="37479-111">Unité utilisée pour la préparation de l’État.</span><span class="sxs-lookup"><span data-stu-id="37479-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="37479-112">OPS : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="37479-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="37479-113">Les opérateurs de mesure du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="37479-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="37479-114">coeffs : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="37479-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="37479-115">Coefficients du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="37479-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="37479-116">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="37479-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="37479-117">Nombre de qubits nécessaires pour simuler le système moléculaire.</span><span class="sxs-lookup"><span data-stu-id="37479-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="37479-118">nSamples : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="37479-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="37479-119">Nombre d’échantillons à utiliser pour l’estimation du terme attendu.</span><span class="sxs-lookup"><span data-stu-id="37479-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="37479-120">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37479-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37479-121">Énergie associée au terme de Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="37479-121">The energy associated to the Jordan-Wigner term.</span></span>