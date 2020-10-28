---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Opération CCNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702139"
---
# <a name="ccnot-operation"></a><span data-ttu-id="90d7b-102">Opération CCNOT</span><span class="sxs-lookup"><span data-stu-id="90d7b-102">CCNOT operation</span></span>

<span data-ttu-id="90d7b-103">Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="90d7b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="90d7b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90d7b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90d7b-105">Applique la porte doublement contrôlée-NOT (CCNOT) à trois qubits.</span><span class="sxs-lookup"><span data-stu-id="90d7b-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="90d7b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="90d7b-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="90d7b-107">Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="90d7b-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="90d7b-108">Premier contrôle qubit pour la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="90d7b-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="90d7b-109">Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="90d7b-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="90d7b-110">Deuxième contrôle qubit pour la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="90d7b-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="90d7b-111">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="90d7b-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="90d7b-112">Qubit cible de la porte CCNOT.</span><span class="sxs-lookup"><span data-stu-id="90d7b-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90d7b-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90d7b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="90d7b-114">Notes</span><span class="sxs-lookup"><span data-stu-id="90d7b-114">Remarks</span></span>

<span data-ttu-id="90d7b-115">Équivalent à :</span><span class="sxs-lookup"><span data-stu-id="90d7b-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```