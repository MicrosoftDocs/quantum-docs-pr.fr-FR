---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: Opération ApplyInnerTTKAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707635"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="c4ba8-102">Opération ApplyInnerTTKAdder</span><span class="sxs-lookup"><span data-stu-id="c4ba8-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="c4ba8-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c4ba8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c4ba8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4ba8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4ba8-105">Implémente la fonction d’addition interne pour l’opération RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="c4ba8-106">Il s’agit de l’opération interne qui est conjuguée avec l’opération externe pour construire l’Adder complet.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c4ba8-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="c4ba8-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c4ba8-108">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c4ba8-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c4ba8-109">LittleEndian qubit Register Encoding la première entrée opérande entière à RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c4ba8-110">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c4ba8-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c4ba8-111">LittleEndian qubit Register Encoding the second entier opérande input to RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="c4ba8-112">transporter : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c4ba8-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c4ba8-113">Transporter qubit, est XOR avec le bit le plus significatif de la somme.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4ba8-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4ba8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c4ba8-115">Notes</span><span class="sxs-lookup"><span data-stu-id="c4ba8-115">Remarks</span></span>

<span data-ttu-id="c4ba8-116">L’opération contrôlée spécifiée utilise la symétrie et l’annulation mutuelle des opérations pour améliorer l’implémentation par défaut qui ajoute un contrôle à chaque opération.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="c4ba8-117">Références</span><span class="sxs-lookup"><span data-stu-id="c4ba8-117">References</span></span>

- <span data-ttu-id="c4ba8-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro : « circuits d’addition quantiques et sortants non liés », informations de Quantum et calcul, vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530