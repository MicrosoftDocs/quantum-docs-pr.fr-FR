---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: Opération ApplyInnerTTKAdderWithoutCarry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707627"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="6f5ee-102">Opération ApplyInnerTTKAdderWithoutCarry</span><span class="sxs-lookup"><span data-stu-id="6f5ee-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="6f5ee-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6f5ee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6f5ee-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f5ee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f5ee-105">Implémente la fonction d’addition interne pour l’opération RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="6f5ee-106">Il s’agit de l’opération interne qui est conjuguée avec l’opération externe pour construire l’Adder complet.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6f5ee-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="6f5ee-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="6f5ee-108">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6f5ee-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6f5ee-109">LittleEndian qubit Register Encoding la première entrée opérande entière à RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="6f5ee-110">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6f5ee-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6f5ee-111">LittleEndian qubit Register Encoding the second entier opérande input to RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f5ee-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f5ee-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6f5ee-113">Notes</span><span class="sxs-lookup"><span data-stu-id="6f5ee-113">Remarks</span></span>

<span data-ttu-id="6f5ee-114">L’opération contrôlée spécifiée utilise la symétrie et l’annulation mutuelle des opérations pour améliorer l’implémentation par défaut qui ajoute un contrôle à chaque opération.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="6f5ee-115">Références</span><span class="sxs-lookup"><span data-stu-id="6f5ee-115">References</span></span>

- <span data-ttu-id="6f5ee-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro : « circuits d’addition quantiques et sortants non liés », informations de Quantum et calcul, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="6f5ee-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530