---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Opération ReflectAboutInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706339"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="55c7d-102">Opération ReflectAboutInteger</span><span class="sxs-lookup"><span data-stu-id="55c7d-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="55c7d-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="55c7d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="55c7d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55c7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55c7d-105">Reflète un registre quantique sur un entier classique donné.</span><span class="sxs-lookup"><span data-stu-id="55c7d-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="55c7d-106">Description</span><span class="sxs-lookup"><span data-stu-id="55c7d-106">Description</span></span>

<span data-ttu-id="55c7d-107">À partir d’un registre Quantum initialement dans l’État $ \ sum_i \ alpha_i \ket{i} $, où chaque $ \ket{i} $ est un état de base représentant un entier $i $, reflète l’état du Registre à propos de l’état de base pour un entier donné $ \ket{j} $, $ $ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="55c7d-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="55c7d-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="55c7d-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="55c7d-109">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55c7d-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55c7d-110">Entier classique qui indexe l’état de base à partir duquel refléter.</span><span class="sxs-lookup"><span data-stu-id="55c7d-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="55c7d-111">Reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="55c7d-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="55c7d-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55c7d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="55c7d-113">Notes</span><span class="sxs-lookup"><span data-stu-id="55c7d-113">Remarks</span></span>

<span data-ttu-id="55c7d-114">Cette opération est implémentée sur place, sans allocation explicite de qubits auxiliaire supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="55c7d-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>