---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: Opération ApplyInnerTTKAdderWithoutCarry
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 656dc947ab88a7e7f1e8e8722c5262470307f7dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190953"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="d3f67-102">Opération ApplyInnerTTKAdderWithoutCarry</span><span class="sxs-lookup"><span data-stu-id="d3f67-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="d3f67-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d3f67-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d3f67-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3f67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3f67-105">Implémente la fonction d’addition interne pour l’opération RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="d3f67-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="d3f67-106">Il s’agit de l’opération interne qui est conjuguée avec l’opération externe pour construire l’Adder complet.</span><span class="sxs-lookup"><span data-stu-id="d3f67-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d3f67-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="d3f67-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d3f67-108">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d3f67-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d3f67-109">LittleEndian qubit Register Encoding la première entrée opérande entière à RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="d3f67-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d3f67-110">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d3f67-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d3f67-111">LittleEndian qubit Register Encoding the second entier opérande input to RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="d3f67-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3f67-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3f67-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d3f67-113">Notes</span><span class="sxs-lookup"><span data-stu-id="d3f67-113">Remarks</span></span>

<span data-ttu-id="d3f67-114">L’opération contrôlée spécifiée utilise la symétrie et l’annulation mutuelle des opérations pour améliorer l’implémentation par défaut qui ajoute un contrôle à chaque opération.</span><span class="sxs-lookup"><span data-stu-id="d3f67-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="d3f67-115">Références</span><span class="sxs-lookup"><span data-stu-id="d3f67-115">References</span></span>

- <span data-ttu-id="d3f67-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro : « circuits d’addition quantiques et sortants non liés », informations de Quantum et calcul, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="d3f67-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530