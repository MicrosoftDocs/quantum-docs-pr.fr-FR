---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708183"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="b07b4-102">StatePreparationComplexCoefficients fonction)</span><span class="sxs-lookup"><span data-stu-id="b07b4-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="b07b4-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b07b4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b07b4-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b07b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b07b4-105">Retourne une opération qui prépare un État Quantum spécifique.</span><span class="sxs-lookup"><span data-stu-id="b07b4-105">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="b07b4-106">L’opération retournée $U $ prépare un État Quantum arbitraire $ \ket{\Psi} $ avec des coefficients complexes $r _j e ^ {i t_j} $ de l’état de la base de calcul $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="b07b4-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="b07b4-107">L’action de U sur un registre nouvellement alloué est donnée par $ $ \begin{align} U\ket {0... 0} = \ket{\Psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="b07b4-107">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="b07b4-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b07b4-108">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b07b4-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="b07b4-109">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="b07b4-110">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="b07b4-110">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="b07b4-111">Tableau allant jusqu’à un maximum de $2 ^ n $ de coefficients complexes représentés par leur valeur absolue et la phase $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="b07b4-111">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="b07b4-112">Le $j $ th coefficient indexe le nombre d’États $ \ket{j} $ encodé au format Little endian.</span><span class="sxs-lookup"><span data-stu-id="b07b4-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="b07b4-113">Sortie : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unité](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="b07b4-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b07b4-114">Une opération unitaire de préparation de l’État $U $.</span><span class="sxs-lookup"><span data-stu-id="b07b4-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="b07b4-115">Notes</span><span class="sxs-lookup"><span data-stu-id="b07b4-115">Remarks</span></span>

<span data-ttu-id="b07b4-116">Les coefficients d’entrée négatifs $r _j < $0 sont traités comme s’ils étaient positifs avec la valeur $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="b07b4-116">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="b07b4-117">`coefficients` sera complété avec les éléments $ (r_j, t_j) = (0,0, 0,0) $ si moins de $2 ^ n $ sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="b07b4-117">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>