---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Opération CCNOT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212475"
---
# <a name="ccnot-operation"></a><span data-ttu-id="4df3d-102">Opération CCNOT</span><span class="sxs-lookup"><span data-stu-id="4df3d-102">CCNOT operation</span></span>

<span data-ttu-id="4df3d-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4df3d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4df3d-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4df3d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4df3d-105">Applique la porte doublement contrôlée-NOT (CCNOT) à trois qubits.</span><span class="sxs-lookup"><span data-stu-id="4df3d-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4df3d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4df3d-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="4df3d-107">Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4df3d-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4df3d-108">Premier contrôle qubit pour la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="4df3d-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="4df3d-109">Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4df3d-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4df3d-110">Deuxième contrôle qubit pour la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="4df3d-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4df3d-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4df3d-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4df3d-112">Qubit cible de la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="4df3d-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4df3d-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4df3d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4df3d-114">Notes</span><span class="sxs-lookup"><span data-stu-id="4df3d-114">Remarks</span></span>

<span data-ttu-id="4df3d-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="4df3d-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```