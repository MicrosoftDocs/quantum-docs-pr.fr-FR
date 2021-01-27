---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Opération SetToBasisState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854627"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="520bc-102">Opération SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="520bc-102">SetToBasisState operation</span></span>

<span data-ttu-id="520bc-103">Espace de noms : [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="520bc-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="520bc-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="520bc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="520bc-105">Définit un qubit sur un état de base donné en mesurant le qubit et en appliquant un retournement binaire, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="520bc-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="520bc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="520bc-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="520bc-107">desired __: <Result> non valide__</span><span class="sxs-lookup"><span data-stu-id="520bc-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="520bc-108">État de base auquel le qubit doit être défini.</span><span class="sxs-lookup"><span data-stu-id="520bc-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="520bc-109">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="520bc-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="520bc-110">Qubit dont l’État doit être défini.</span><span class="sxs-lookup"><span data-stu-id="520bc-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="520bc-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="520bc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="520bc-112">Notes</span><span class="sxs-lookup"><span data-stu-id="520bc-112">Remarks</span></span>

<span data-ttu-id="520bc-113">Comme un invariant de cette opération, l’appel de `M(q)` juste après `SetToBasisState(result, q)` retourne `result` .</span><span class="sxs-lookup"><span data-stu-id="520bc-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>