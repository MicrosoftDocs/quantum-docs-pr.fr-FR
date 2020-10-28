---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Opération AssertPhase
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702745"
---
# <a name="assertphase-operation"></a><span data-ttu-id="06b15-102">Opération AssertPhase</span><span class="sxs-lookup"><span data-stu-id="06b15-102">AssertPhase operation</span></span>

<span data-ttu-id="06b15-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="06b15-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="06b15-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06b15-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06b15-105">Déclare que la phase d’un état de superposition égal a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="06b15-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="06b15-106">Description</span><span class="sxs-lookup"><span data-stu-id="06b15-106">Description</span></span>

<span data-ttu-id="06b15-107">Cette opération déclare que la phase $ \Phi $ d’un État Quantum qui peut être exprimée sous la forme $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ Ket {0} + e ^ {-i\phi} \ Ket {1} ) $ pour un réel réel $t $ a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="06b15-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="06b15-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="06b15-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="06b15-109">ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06b15-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06b15-110">La valeur attendue de $ \Phi \Dans (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="06b15-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="06b15-111">qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="06b15-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="06b15-112">Qubit qui stocke l’État attendu.</span><span class="sxs-lookup"><span data-stu-id="06b15-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="06b15-113">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06b15-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06b15-114">Tolérance absolue sur la différence entre réel et attendu.</span><span class="sxs-lookup"><span data-stu-id="06b15-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="06b15-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06b15-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

