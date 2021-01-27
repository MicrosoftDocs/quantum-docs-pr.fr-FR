---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Opération AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843401"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="6666f-102">Opération AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="6666f-102">AssertProbInt operation</span></span>

<span data-ttu-id="6666f-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6666f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6666f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6666f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6666f-105">Déclare que la probabilité d’un état spécifique d’un registre Quantum a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="6666f-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="6666f-106">Description</span><span class="sxs-lookup"><span data-stu-id="6666f-106">Description</span></span>

<span data-ttu-id="6666f-107">À partir d’un $n $-qubit Quantum State $ \ket{\Psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, déclare que la probabilité $ | \ alpha_j | ^ 2 $ de l’État $ \ket{j} $ indexée par $j $ a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="6666f-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="6666f-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="6666f-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="6666f-109">stateIndex : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6666f-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6666f-110">L’index $j $ de l’État $ \ket{j} $ représenté par un `LittleEndian` Registre.</span><span class="sxs-lookup"><span data-stu-id="6666f-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="6666f-111">ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6666f-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6666f-112">La valeur attendue de $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="6666f-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6666f-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6666f-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6666f-114">Le registre qubit qui stocke $ \ket{\Psi} $ dans un format avec primauté des octets de poids faible.</span><span class="sxs-lookup"><span data-stu-id="6666f-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="6666f-115">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6666f-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6666f-116">Tolérance absolue sur la différence entre réel et attendu.</span><span class="sxs-lookup"><span data-stu-id="6666f-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6666f-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6666f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="6666f-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="6666f-118">Example</span></span>

<span data-ttu-id="6666f-119">Supposons que le `qubits` Registre encode un État Quantum 3-qubit $ \ket{\Psi} = \ sqrt {1/8} \ Ket {0} + \ sqrt {7/8} \ Ket {6} $ dans un format avec primauté des octets de poids faible (Little-endian).</span><span class="sxs-lookup"><span data-stu-id="6666f-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="6666f-120">Cela signifie que le nombre indique $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ et $ \ket \equiv\ket \ket {6} {0} {1} {1} $.</span><span class="sxs-lookup"><span data-stu-id="6666f-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="6666f-121">Les affirmations suivantes ont ensuite été effectuées :</span><span class="sxs-lookup"><span data-stu-id="6666f-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```