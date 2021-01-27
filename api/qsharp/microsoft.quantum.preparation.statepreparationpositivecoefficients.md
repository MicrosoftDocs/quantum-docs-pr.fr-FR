---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855842"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="804af-102">StatePreparationPositiveCoefficients fonction)</span><span class="sxs-lookup"><span data-stu-id="804af-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="804af-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="804af-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="804af-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="804af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="804af-105">StatePreparationPositiveCoefficients est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="804af-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="804af-106">Utilisez plutôt <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>.</span><span class="sxs-lookup"><span data-stu-id="804af-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="804af-107">Retourne une opération qui prépare l’État Quantum donné.</span><span class="sxs-lookup"><span data-stu-id="804af-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="804af-108">L’opération retournée $U $ prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients $ \ alpha_j \ge $0 à partir de l’état de $n la base de calcul $ qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="804af-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="804af-109">L’action de U sur un registre nouvellement alloué est donnée par $ $ \begin{align} U \ket{0\cdots 0} = \ket{\Psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="804af-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="804af-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="804af-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="804af-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="804af-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="804af-112">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="804af-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="804af-113">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="804af-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="804af-114">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="804af-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="804af-115">Sortie : [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="804af-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="804af-116">Une opération unitaire de préparation de l’État $U $.</span><span class="sxs-lookup"><span data-stu-id="804af-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="804af-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="804af-117">Example</span></span>

<span data-ttu-id="804af-118">L’extrait de code suivant prépare l’État Quantum $ \ket{\Psi} = \ sqrt {1/8} \ Ket {0} + \ sqrt {7/8} \ Ket {2} $ dans le registre qubit `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="804af-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="804af-119">Notes</span><span class="sxs-lookup"><span data-stu-id="804af-119">Remarks</span></span>

<span data-ttu-id="804af-120">Les coefficients d’entrée négatifs $ \ alpha_j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="804af-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="804af-121">`coefficients` sera complété avec les éléments $ \ alpha_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="804af-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>