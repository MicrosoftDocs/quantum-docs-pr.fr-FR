---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 594896a72fe40e5ba994e08500c3ce71b185bfff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193554"
---
# <a name="blochspherecoordinates-function"></a><span data-ttu-id="15301-102">BlochSphereCoordinates fonction)</span><span class="sxs-lookup"><span data-stu-id="15301-102">BlochSphereCoordinates function</span></span>

<span data-ttu-id="15301-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="15301-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="15301-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15301-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15301-105">Calcule les coordonnées de la sphère Bloch pour un État à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="15301-105">Computes the Bloch sphere coordinates for a single-qubit state.</span></span>

<span data-ttu-id="15301-106">Étant donné deux nombres complexes $a 0, a1 $ qui représentent l’État qubit, calcule les coordonnées sur la sphère Bloch, de sorte que $a 0 \ket {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i \Phi/2}\cos{(\ Theta/2)} \ket {0} + e ^ {i \Phi/2}\sin{(\ Theta/2)} \ket {1} ) $.</span><span class="sxs-lookup"><span data-stu-id="15301-106">Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.</span></span>

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a><span data-ttu-id="15301-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="15301-107">Input</span></span>

### <a name="a0--complexpolar"></a><span data-ttu-id="15301-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="15301-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="15301-109">Coefficient complexe de l’État $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="15301-109">Complex coefficient of state $\ket{0}$.</span></span>


### <a name="a1--complexpolar"></a><span data-ttu-id="15301-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="15301-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="15301-111">Coefficient complexe de l’État $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="15301-111">Complex coefficient of state $\ket{1}$.</span></span>



## <a name="output--complexpolardoubledouble"></a><span data-ttu-id="15301-112">Sortie : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[double](xref:microsoft.quantum.lang-ref.double),[double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="15301-112">Output : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="15301-113">Tuple contenant `(ComplexPolar(r, t), phi, theta)` .</span><span class="sxs-lookup"><span data-stu-id="15301-113">A tuple containing `(ComplexPolar(r, t), phi, theta)`.</span></span>