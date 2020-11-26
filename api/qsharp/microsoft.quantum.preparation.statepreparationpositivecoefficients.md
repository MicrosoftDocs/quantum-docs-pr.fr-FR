---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients fonction)
ms.date: 11/25/2020 12:00:00 AM
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
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193248"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="7dd7e-102">StatePreparationPositiveCoefficients fonction)</span><span class="sxs-lookup"><span data-stu-id="7dd7e-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="7dd7e-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7dd7e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7dd7e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7dd7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="7dd7e-105">StatePreparationPositiveCoefficients est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="7dd7e-106">Utilisez plutôt <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD>.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="7dd7e-107">Retourne une opération qui prépare l’État Quantum donné.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="7dd7e-108">L’opération retournée $U $ prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients $ \ alpha_j \ge $0 à partir de l’état de $n la base de calcul $ qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="7dd7e-109">L’action de U sur un registre nouvellement alloué est donnée par $ $ \begin{align} U \ket{0\cdots 0} = \ket{\Psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="7dd7e-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7dd7e-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="7dd7e-111">Entrée</span><span class="sxs-lookup"><span data-stu-id="7dd7e-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="7dd7e-112">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7dd7e-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7dd7e-113">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="7dd7e-114">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="7dd7e-115">Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unité](xref:microsoft.quantum.lang-ref.unit) LittleEndian est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="7dd7e-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7dd7e-116">Une opération unitaire de préparation de l’État $U $.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="7dd7e-117">Notes</span><span class="sxs-lookup"><span data-stu-id="7dd7e-117">Remarks</span></span>

<span data-ttu-id="7dd7e-118">Les coefficients d’entrée négatifs $ \ alpha_j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-118">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="7dd7e-119">`coefficients` sera complété avec les éléments $ \ alpha_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="7dd7e-119">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>