---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708177"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="4c65c-102">StatePreparationPositiveCoefficients fonction)</span><span class="sxs-lookup"><span data-stu-id="4c65c-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="4c65c-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="4c65c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="4c65c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c65c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c65c-105">Retourne une opération qui prépare l’État Quantum donné.</span><span class="sxs-lookup"><span data-stu-id="4c65c-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="4c65c-106">L’opération retournée $U $ prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients $ \ alpha_j \ge $0 à partir de l’état de $n la base de calcul $ qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="4c65c-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="4c65c-107">L’action de U sur un registre nouvellement alloué est donnée par $ $ \begin{align} U \ket{0\cdots 0} = \ket{\Psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="4c65c-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="4c65c-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="4c65c-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4c65c-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="4c65c-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="4c65c-110">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4c65c-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4c65c-111">Tableau allant jusqu’à $2 ^ n $ coefficients $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="4c65c-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="4c65c-112">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="4c65c-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="4c65c-113">Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="4c65c-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4c65c-114">Une opération unitaire de préparation de l’État $U $.</span><span class="sxs-lookup"><span data-stu-id="4c65c-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c65c-115">Notes</span><span class="sxs-lookup"><span data-stu-id="4c65c-115">Remarks</span></span>

<span data-ttu-id="4c65c-116">Les coefficients d’entrée négatifs $ \ alpha_j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="4c65c-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="4c65c-117">`coefficients` sera complété avec les éléments $ \ alpha_j = $0,0 si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="4c65c-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>