---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Opération CCNOT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819026"
---
# <a name="ccnot-operation"></a><span data-ttu-id="7f98a-102">Opération CCNOT</span><span class="sxs-lookup"><span data-stu-id="7f98a-102">CCNOT operation</span></span>

<span data-ttu-id="7f98a-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7f98a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7f98a-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7f98a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7f98a-105">Applique la porte doublement contrôlée-NOT (CCNOT) à trois qubits.</span><span class="sxs-lookup"><span data-stu-id="7f98a-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7f98a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7f98a-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="7f98a-107">Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7f98a-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7f98a-108">Premier contrôle qubit pour la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="7f98a-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="7f98a-109">Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7f98a-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7f98a-110">Deuxième contrôle qubit pour la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="7f98a-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7f98a-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7f98a-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7f98a-112">Qubit cible de la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="7f98a-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f98a-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f98a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7f98a-114">Notes</span><span class="sxs-lookup"><span data-stu-id="7f98a-114">Remarks</span></span>

<span data-ttu-id="7f98a-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="7f98a-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```