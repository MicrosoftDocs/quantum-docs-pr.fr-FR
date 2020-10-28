---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Opération AssertProbInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707438"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="3133b-102">Opération AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="3133b-102">AssertProbInt operation</span></span>

<span data-ttu-id="3133b-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3133b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3133b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3133b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3133b-105">Déclare que la probabilité d’un état spécifique d’un registre Quantum a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="3133b-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="3133b-106">Description</span><span class="sxs-lookup"><span data-stu-id="3133b-106">Description</span></span>

<span data-ttu-id="3133b-107">À partir d’un $n $-qubit Quantum State $ \ket{\Psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, déclare que la probabilité $ | \ alpha_j | ^ 2 $ de l’État $ \ket{j} $ indexée par $j $ a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="3133b-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="3133b-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="3133b-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="3133b-109">stateIndex : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3133b-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3133b-110">L’index $j $ de l’État $ \ket{j} $ représenté par un `LittleEndian` Registre.</span><span class="sxs-lookup"><span data-stu-id="3133b-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="3133b-111">ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3133b-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3133b-112">La valeur attendue de $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="3133b-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3133b-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3133b-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3133b-114">Le registre qubit qui stocke $ \ket{\Psi} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="3133b-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="3133b-115">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3133b-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3133b-116">Tolérance absolue sur la différence entre réel et attendu.</span><span class="sxs-lookup"><span data-stu-id="3133b-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3133b-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3133b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

