---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Opération AssertQubitIsInStateWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202207"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="a9f72-102">Opération AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="a9f72-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="a9f72-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a9f72-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a9f72-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a9f72-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a9f72-105">Déclare qu’un qubit dans l’État attendu.</span><span class="sxs-lookup"><span data-stu-id="a9f72-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="a9f72-106">`expected` représente un vecteur complexe, $ \ket{\Psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.</span><span class="sxs-lookup"><span data-stu-id="a9f72-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="a9f72-107">Le premier élément des tuples représentant chacun des $a $, $b $ est la partie réelle du nombre complexe, tandis que le deuxième est la partie imaginaire.</span><span class="sxs-lookup"><span data-stu-id="a9f72-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="a9f72-108">Le dernier argument définit la tolérance avec laquelle l’assertion est faite.</span><span class="sxs-lookup"><span data-stu-id="a9f72-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="a9f72-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="a9f72-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="a9f72-110">ATTENDU : ([complexe](xref:Microsoft.Quantum.Math.Complex),[complexe](xref:Microsoft.Quantum.Math.Complex))</span><span class="sxs-lookup"><span data-stu-id="a9f72-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="a9f72-111">Amplitudes complexes attendues pour $ \ket {0} $ et $ \ket {1} $, respectivement.</span><span class="sxs-lookup"><span data-stu-id="a9f72-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="a9f72-112">inscription : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a9f72-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a9f72-113">Qubit dont l’État doit être déclaré.</span><span class="sxs-lookup"><span data-stu-id="a9f72-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="a9f72-114">Notez que ce qubit est supposé être séparable des autres qubits alloués et non pris en compte.</span><span class="sxs-lookup"><span data-stu-id="a9f72-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a9f72-115">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9f72-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a9f72-116">Tolérance additive par laquelle les amplitudes réelles sont autorisées à s’écarter de la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="a9f72-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="a9f72-117">Pour plus d’informations, consultez les remarques ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a9f72-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9f72-118">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9f72-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a9f72-119">Notes</span><span class="sxs-lookup"><span data-stu-id="a9f72-119">Remarks</span></span>

<span data-ttu-id="a9f72-120">Le code Mathematica suivant peut être utilisé pour vérifier les expressions pour mi, MX, My, MZ :</span><span class="sxs-lookup"><span data-stu-id="a9f72-120">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="a9f72-121">La tolérance est le $L de la \_ distance {\infty} $ entre le vecteur réel à 3 Dimensions (x ₂, x ₃, x ₄) défini par $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ et Real vector (y ₂, y ₃, y ₄) défini par p = y ₁ I + y ₂ x + y ₃ y + y ₄ Z où p est la matrice de densité correspondant à l’état du Registre.</span><span class="sxs-lookup"><span data-stu-id="a9f72-121">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="a9f72-122">Cela est vrai uniquement en supposant que TR (p) et TR (| ψ ⟩ ⟨ ψ |) sont tous deux 1 (par exemple, x ₁ = 1/2, y ₁ = 1/2).</span><span class="sxs-lookup"><span data-stu-id="a9f72-122">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="a9f72-123">Si ce n’est pas le cas, la fonction déclare que la distance l ∞ entre (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) et (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) est inférieure au paramètre Tolerance.</span><span class="sxs-lookup"><span data-stu-id="a9f72-123">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>