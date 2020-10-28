---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Opération ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709179"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="a2b25-102">Opération ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="a2b25-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="a2b25-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a2b25-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a2b25-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2b25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2b25-105">Applique l' @"microsoft.quantum.intrinsic.x" opération sur `target` , si la fonction booléenne `func` prend la valeur true pour l’assignation classique dans `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="a2b25-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="a2b25-106">Description</span><span class="sxs-lookup"><span data-stu-id="a2b25-106">Description</span></span>

<span data-ttu-id="a2b25-107">Cette opération implémente un cas particulier de @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , dans lequel le qubit cible est connu comme étant dans l’état $ {0} \ket $.</span><span class="sxs-lookup"><span data-stu-id="a2b25-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="a2b25-108">L’implémentation utilise des @"microsoft.quantum.intrinsic.cnot" portes et @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="a2b25-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="a2b25-109">L’implémentation de l’opération joint est optimisée et utilise le décalcul basé sur les mesures.</span><span class="sxs-lookup"><span data-stu-id="a2b25-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="a2b25-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="a2b25-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="a2b25-111">Func : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a2b25-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a2b25-112">Table de vérité booléenne représentée comme grand entier</span><span class="sxs-lookup"><span data-stu-id="a2b25-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="a2b25-113">controlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a2b25-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a2b25-114">Registre de contrôle qubits</span><span class="sxs-lookup"><span data-stu-id="a2b25-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a2b25-115">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a2b25-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a2b25-116">Qubit cible (doit être dans l’État $ \ket {0} $)</span><span class="sxs-lookup"><span data-stu-id="a2b25-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2b25-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2b25-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a2b25-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a2b25-118">See Also</span></span>

- [<span data-ttu-id="a2b25-119">Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="a2b25-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)