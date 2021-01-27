---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Opération ApplyOuterCDKMAdder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: acaa563245bb7c701316d2dfd35b5be03d8e024d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843703"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="e5dd8-102">Opération ApplyOuterCDKMAdder</span><span class="sxs-lookup"><span data-stu-id="e5dd8-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="e5dd8-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e5dd8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e5dd8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5dd8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5dd8-105">Opération de transport d’ondulations sur place réversible qui est utilisée dans l’opération d’addition d’entiers RippleCarryAdderCDKM ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e5dd8-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="e5dd8-106">À partir de deux registres qubit `xs` et `ys` de la même longueur, l’opération applique une séquence d’ondulations de CNOTIN et CCNOT portes avec qubits dans `xs` et `ys` en tant que contrôles et qubits dans `xs` comme cibles.</span><span class="sxs-lookup"><span data-stu-id="e5dd8-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e5dd8-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="e5dd8-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e5dd8-108">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5dd8-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e5dd8-109">Premier registre qubit, contenant les contrôles et les cibles.</span><span class="sxs-lookup"><span data-stu-id="e5dd8-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e5dd8-110">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e5dd8-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e5dd8-111">Deuxième Registre qubit, qui contribue aux contrôles.</span><span class="sxs-lookup"><span data-stu-id="e5dd8-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="e5dd8-112">Ancilla : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e5dd8-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e5dd8-113">Ancilla qubit utilisé dans RippleCarryAdderCDKM passé à cette opération.</span><span class="sxs-lookup"><span data-stu-id="e5dd8-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e5dd8-114">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5dd8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e5dd8-115">Références</span><span class="sxs-lookup"><span data-stu-id="e5dd8-115">References</span></span>

- <span data-ttu-id="e5dd8-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton : « A New Quantum ondulation-Carry apporting circuit », 2004.</span><span class="sxs-lookup"><span data-stu-id="e5dd8-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1