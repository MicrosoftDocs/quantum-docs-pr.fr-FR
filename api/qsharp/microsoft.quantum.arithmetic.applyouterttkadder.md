---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: Opération ApplyOuterTTKAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707571"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="22703-102">Opération ApplyOuterTTKAdder</span><span class="sxs-lookup"><span data-stu-id="22703-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="22703-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="22703-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="22703-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22703-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22703-105">Implémente l’opération externe pour RippleCarryAdderTTK pour conjuguer l’opération interne afin de construire l’Adder complet.</span><span class="sxs-lookup"><span data-stu-id="22703-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="22703-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="22703-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="22703-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="22703-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="22703-108">LittleEndian qubit Register Encoding la première entrée opérande entière à RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="22703-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="22703-109">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="22703-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="22703-110">LittleEndian qubit Register Encoding the second entier opérande input to RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="22703-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="22703-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22703-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="22703-112">Références</span><span class="sxs-lookup"><span data-stu-id="22703-112">References</span></span>

- <span data-ttu-id="22703-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro : « circuits d’addition quantiques et sortants non liés », informations de Quantum et calcul, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="22703-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530