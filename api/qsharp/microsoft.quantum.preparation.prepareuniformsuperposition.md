---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Opération PrepareUniformSuperposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701248"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="34981-102">Opération PrepareUniformSuperposition</span><span class="sxs-lookup"><span data-stu-id="34981-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="34981-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="34981-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="34981-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34981-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34981-105">Crée une superposition uniforme sur les États qui encodent 0 à `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="34981-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="34981-106">Autrement dit, ce $U unitaire $ crée une superposition uniforme sur tous les États numériques $0 $ à $M-$1, étant donné un état d’entrée $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="34981-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="34981-107">En d’autres termes, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="34981-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="34981-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="34981-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="34981-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="34981-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="34981-110">nIndices : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="34981-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="34981-111">Nombre souhaité d’États $M $ dans la superposition uniforme.</span><span class="sxs-lookup"><span data-stu-id="34981-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="34981-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="34981-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="34981-113">Registre qubit qui stocke les États du nombre au `LittleEndian` format.</span><span class="sxs-lookup"><span data-stu-id="34981-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="34981-114">Ce registre doit être en mesure de stocker le nombre $M-$1, et est supposé être initialisé à l’État $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="34981-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="34981-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34981-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="34981-116">Notes</span><span class="sxs-lookup"><span data-stu-id="34981-116">Remarks</span></span>

<span data-ttu-id="34981-117">L’opération est adjointable, mais requiert `indexRegister` une superposition uniforme sur les États de la première `nIndices` base dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="34981-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>