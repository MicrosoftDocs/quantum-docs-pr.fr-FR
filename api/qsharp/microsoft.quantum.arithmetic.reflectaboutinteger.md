---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Opération ReflectAboutInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842972"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="72f38-102">Opération ReflectAboutInteger</span><span class="sxs-lookup"><span data-stu-id="72f38-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="72f38-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="72f38-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="72f38-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72f38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72f38-105">Reflète un registre quantique sur un entier classique donné.</span><span class="sxs-lookup"><span data-stu-id="72f38-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="72f38-106">Description</span><span class="sxs-lookup"><span data-stu-id="72f38-106">Description</span></span>

<span data-ttu-id="72f38-107">À partir d’un registre Quantum initialement dans l’État $ \ sum_i \ alpha_i \ket{i} $, où chaque $ \ket{i} $ est un état de base représentant un entier $i $, reflète l’état du Registre à propos de l’état de base pour un entier donné $ \ket{j} $, $ $ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="72f38-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="72f38-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="72f38-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="72f38-109">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72f38-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72f38-110">Entier classique qui indexe l’état de base à partir duquel refléter.</span><span class="sxs-lookup"><span data-stu-id="72f38-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="72f38-111">Reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="72f38-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="72f38-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72f38-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="72f38-113">Notes</span><span class="sxs-lookup"><span data-stu-id="72f38-113">Remarks</span></span>

<span data-ttu-id="72f38-114">Cette opération est implémentée sur place, sans allocation explicite de qubits auxiliaire supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="72f38-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>