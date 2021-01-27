---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Opération AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830076"
---
# <a name="assertphase-operation"></a><span data-ttu-id="c8428-102">Opération AssertPhase</span><span class="sxs-lookup"><span data-stu-id="c8428-102">AssertPhase operation</span></span>

<span data-ttu-id="c8428-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c8428-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c8428-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8428-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8428-105">Déclare que la phase d’un état de superposition égal a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="c8428-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="c8428-106">Description</span><span class="sxs-lookup"><span data-stu-id="c8428-106">Description</span></span>

<span data-ttu-id="c8428-107">Cette opération déclare que la phase $ \Phi $ d’un État Quantum qui peut être exprimée sous la forme $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ Ket {0} + e ^ {-i\phi} \ Ket {1} ) $ pour un réel réel $t $ a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="c8428-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="c8428-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c8428-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="c8428-109">ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8428-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c8428-110">La valeur attendue de $ \Phi \Dans (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="c8428-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c8428-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c8428-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c8428-112">Qubit qui stocke l’État attendu.</span><span class="sxs-lookup"><span data-stu-id="c8428-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="c8428-113">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8428-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c8428-114">Tolérance absolue sur la différence entre réel et attendu.</span><span class="sxs-lookup"><span data-stu-id="c8428-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8428-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8428-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="c8428-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="c8428-116">Example</span></span>

<span data-ttu-id="c8428-117">L’assertion suivante aboutit : `qubit` est dans l’État $ \ket{\Psi} = e ^ {i 0,5} \ sqrt {1/2} \ Ket {0} + e ^ {i 0.5} \ sqrt {1/2} \ Ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="c8428-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="c8428-118">`qubit` est dans l’État $ \ket{\Psi} = e ^ {i 0,5} \ racine {1/2} \ Ket {0} + e ^ {-i 0,5} \ racine {1/2} \ Ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="c8428-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="c8428-119">`qubit` est dans l’État $ \ket{\Psi} = e ^ {-i 2.2} \ racine {1/2} \ Ket {0} + e ^ {i 0,2} \ racine {1/2} \ Ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="c8428-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`